# cass2-a
import java.util.*;
import java.io.*;

class cass{
	public static void main(String args[])throws Exception{
		int k,n,i;
		int n1=0;
		Scanner sc = new Scanner(System.in);
		System.out.println("Enter the key");
		StringBuilder output = new StringBuilder("");
		StringBuilder output1 = new StringBuilder("");
        
		k = sc.nextInt();
		InputStream in = new FileInputStream(new File("C:\\Users\\FY-COM 012\\Desktop\\Mukesh.txt"));
        BufferedReader reader = new BufferedReader(new InputStreamReader(in));
        FileWriter fw = new FileWriter(new File("C:\\Users\\FY-COM 012\\Desktop\\Mukesh1.txt"));
		BufferedWriter bw = new BufferedWriter(fw);
		FileWriter fw1 = new FileWriter(new File("C:\\Users\\FY-COM 012\\Desktop\\Mukesh2.txt"));
		BufferedWriter bw1 = new BufferedWriter(fw1);
		String input = reader.readLine();
        input=input.toLowerCase();
		char[] inputarray = input.toCharArray();
		for(i=0 ; i<inputarray.length; i++){
			n = (int)inputarray[i];
			n = n-97;
			n = (n+k)%26;
			n = n+97;
			output.append((char)n);
		}	
		bw.write(output.toString());
		bw.close();
		reader.close();
		InputStream mn = new FileInputStream(new File("C:\\Users\\FY-COM 012\\Desktop\\Mukesh1.txt"));
        BufferedReader reader1 = new BufferedReader(new InputStreamReader(mn));
        String input1 = reader1.readLine();
		input1=input1.toLowerCase();
	    char[] inpuarray = input1.toCharArray();
	    for(i=0 ; i<inpuarray.length; i++){
			n = (int)inpuarray[i];
			n = n-97;
			n = ((n+26)-k)%26;
			n = n+97;
			output1.append((char)n);
		}	
		
       bw1.write(output1.toString());
		bw1.close();
		reader1.close();
		sc.close();
	}
}
