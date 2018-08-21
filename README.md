# JavaFileHandling
//Copy or Move a file from one location in the file system to another using JAVA.
import java.io.IOException;
import java.nio.file.FileSystem;
import java.nio.file.FileSystems;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.StandardCopyOption;
public class CopyMoveFile {
  public static void main(String args[]) {
    FileSystem fileSys = FileSystems.getDefault();
    Path srcPath = fileSys.getPath("c:\\src_folder\\file1.txt");
    Path destPath = fileSys.getPath("c:\\dest_folder\\file1.txt");
    try {
      //TO COPY file1.txt from source to destination folder
      Files.copy(srcPath, destPath, StandardCopyOption.REPLACE_EXISTING);
       
      //TO MOVE file1.txt from source to destination folder
      Files.move(srcPath, destPath, StandardCopyOption.REPLACE_EXISTING);
    } catch (IOException ioe) {
      ioe.printStackTrace();
    }
  }
}
