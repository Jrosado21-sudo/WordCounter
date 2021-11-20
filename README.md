/Made by: Jose Rosado   
//Purpose: Word counter and Analyzer
//Date:11/19/21

import java.io.FileInputStream;
import java.util.ArrayList; import java.util.Scanner; import java.io.IOException;
/**
 * 
 * @author Jrosa
 *@version 11/19/2021
 */
public class wordcounter {

//import Fileinput stream and scanner
/**
 * 
 * @param args part of the exception
 * @throws IOException part of main
 */
public static void main(String[] args)throws IOException {

	FileInputStream fin = new FileInputStream("C:\\Users\\Jrosa\\Documents\\poem.txt");
	Scanner fileInput = new Scanner(fin);
// Make the arraylists

	ArrayList<String> words = new ArrayList<String>();
	ArrayList<Integer> count = new ArrayList<Integer>();
//Read File and find words

	while(fileInput.hasNext()) {
// Count words

		String nextword = fileInput.next();
//find out if the word is in the Arraylist

		if(words.contains(nextword)){
			int index=words.indexOf(nextword);
			count.set(index,count.get(index)+1);
		}
		else {
			words.add(nextword);
			count.add(1);
		}
	}
	//close
	fileInput.close();
	fin.close();
	
	//show results
	for(int i = 0;i< words.size(); i++) {
		System.out.println(words.get(i) + " occured "+ count.get(i)+" Times ");
		
		
	}
}
}
