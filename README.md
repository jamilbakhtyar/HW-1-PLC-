# HW-1-PLC-
/*Spring 2020*/

/* Jamil Bakhtyar PLC HW1*/
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;


public class PLC1 {

	public static void main(String[] args) {
		String case1 = "2345 6tgbsauhd9sa67*l{OPKDSl;jaklhl";
		String case2 = "Pr*o$of th@t co*d%e work$s";
		List<String> ListOfTok = parseT(case1);
		
		for(int i = 0; i<ListOfTok.size(); i++) {
			System.out.println(ListOfTok.get(i));
		}
	}
	public static List<String> parseT(String inputString){
		List<String> t = new ArrayList<>();
		String alpha = "((?<=%1$s)|(?=%1$s))";
		String[] emptySpace = inputString.split(String.format(alpha, "[^\\w]"));
		
		
		for(int i = 0; i < emptySpace.length; i++) {
			if(!(emptySpace[i].isEmpty())&&(emptySpace[i].trim().length() > 0)) {
				t.add(emptySpace[i]);
			}
		}
		
		return t;
	}

}
