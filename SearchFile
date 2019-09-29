package com.java.searchFile;

import java.io.*;
import java.util.Scanner;
import java.util.regex.Pattern;
public class SearchFile {
	//method to find the files in home directory
	public void find(String directory_path, String regex_pattern) {
		//here creating the file type object.
		File directory =new File(directory_path);
		//taking all files in the directory into a file list
		File[] list=directory.listFiles();
		if(list==null) {
			//checking whether list contains files or not
			System.out.println("Empty Directory");
			return;
		}
		//iterating through files and directories inside home directory
		for(File item:list) {
			if(item.isDirectory()) {
				//if it a directory the method is called again in recursive way
				find(item.getAbsolutePath(), regex_pattern);
			}
			else if(Pattern.matches(regex_pattern, item.getName())) {
					System.out.println("Pattern Found with :"+item.getAbsolutePath());
			}
			else {
				System.out.println("Pattern Not Found with "+item.getName());
			}
		}
	}	

	public static void main(String[] args) {
		//this the main method
		//creating object of the class
		SearchFile path=new SearchFile();
		Scanner scanner= new Scanner(System.in);
		while(true) {
			String regexPattern=scanner.next();
			path.find("/home/zadmin/Desktop",regexPattern);
		}

	}

}
