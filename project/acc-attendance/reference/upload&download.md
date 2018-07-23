# upload/download

[reference : cusmaker.tistory.com](http://cusmaker.tistory.com/110)

```
package com.board.action;

import java.util.regex.Pattern;

import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

import com.board.beans.Board;
import com.board.controller.CommandAction;
import com.board.dao.BoardDao;
import com.oreilly.servlet.MultipartRequest;
import com.oreilly.servlet.multipart.DefaultFileRenamePolicy;

public class InsertAction implements CommandAction{

	@Override
	public String requestPro(HttpServletRequest request, HttpServletResponse response) throws Throwable {
		request.setCharacterEncoding("euc-kr");

		MultipartRequest multi = null;
		int sizeLimit = 10*1024*1024;
		String savePath = "C:\\Users\\gramgram\\eclipse-workspace\\board\\WebContent\\upload";
		try {
			multi = new MultipartRequest(request, savePath, sizeLimit, "euc-kr", new DefaultFileRenamePolicy());
		}catch(Exception e) {
			e.printStackTrace();
		}
		String filename = multi.getFilesystemName("filename");
		String title = multi.getParameter("title");
		String writer = multi.getParameter("writer");
		String password = multi.getParameter("password");
		int count=0;
		String animal = multi.getParameter("animal");
		String content = multi.getParameter("content");
		String regip = request.getRemoteAddr();

		if(title==""||title==null) System.out.println("title이 null입니다.");
		
		if(writer==""||writer==null)
			System.out.println("writer가 null입니다.");
		else if(!Pattern.matches("^[_0-9a-zA-Z-]+@[0-9a-zA-Z-]+(.[_0-9a-zA-Z-]+)*$", writer))
			System.out.println("이메일 형식이 아닙니다.");

		
		if(animal==""||animal==null) System.out.println("animal이 null입니다.");
		
		if(content==""||content==null) System.out.println("content가 null입니다.");

		Board article = new Board();
		
		article.setFilename(filename);
		article.setRegip(regip);
		article.setTitle(title);
		article.setWriter(writer);
		article.setPassword(password);
		article.setAnimal(animal);
		article.setContent(content);
		article.setCount(count);
		BoardDao.getInstance().insertArticle(article);
		
		return "insert.jsp";
	}

}

```

```
package com.board.action;

import java.io.BufferedInputStream;
import java.io.BufferedOutputStream;
import java.io.File;
import java.io.FileInputStream;
import java.net.URLEncoder;

import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

import com.board.beans.Board;
import com.board.controller.CommandAction;
import com.board.dao.BoardDao;

public class DownloadAction implements CommandAction {

	@Override
	public String requestPro(HttpServletRequest request, HttpServletResponse response) throws Throwable {
		request.setCharacterEncoding("euc-kr");
		int idx = Integer.parseInt(request.getParameter("idx"));
		
		Board article = BoardDao.getInstance().getArticle(idx);
		String filename = article.getFilename();
		
		String uploadFileName = "C:\\Users\\gramgram\\eclipse-workspace\\board\\WebContent\\upload/"+filename;
		File downFile = new File(uploadFileName);
		
		if(downFile.exists()&&downFile.isFile()) {
			try {
				long filesize = downFile.length();
				response.setContentType("application/x-msdownload");
				response.setContentLength((int)filesize);
				
				String strClient = request.getHeader("user-agent");
			
				if(strClient.indexOf("MISE 5.5")!=-1) {
					response.setHeader("Content-Disposition","filename=" + filename + ";" );
				}else {
					filename = URLEncoder.encode(filename, "UTF-8").replaceAll("\\+","%20");
					response.setHeader("Content-Disposition","attachment; filename=" + filename + ";" );

				}
				
				response.setHeader("Content-Length",String.valueOf(filesize));
				response.setHeader("Content-Transfer-Encoding", "binary;");
				response.setHeader("Pragma", "no-cache");
				response.setHeader("Cache-Control", "private");
				
				byte b[] = new byte[1024];
				BufferedInputStream fin = new BufferedInputStream(new FileInputStream(downFile));
				BufferedOutputStream outs = new BufferedOutputStream(response.getOutputStream());

				int read = 0;
				while((read=fin.read(b)) != -1){
					outs.write(b, 0, read);
				}

				outs.flush();
				outs.close();
				fin.close();
			
			} catch(Exception e){
				System.out.println("Download Exception : " + e.getMessage());
			}
		}else{
			System.out.println("Download Error : downFile Error [" + downFile + "]");
		}
		return null;
	}
}
```

