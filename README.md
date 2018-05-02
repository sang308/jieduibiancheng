# jieduibiancheng
package qiheng.wei.xianghua.sang;


public class Test_Main {
	public static void main(String[] args) {
		String[] sign = {"+","-","*","/"};
		String[] signNum = new String[30];
		int max = 100;
		int min = 0;
		int numFirst = 0;
		int numSecond = 0;
		double result = 0;
		for(int i = 0 ; i < 30 ; i++ ){
			long seedNumFirst = i + System.currentTimeMillis();
			RandomNum randNumFirst = new RandomNum(seedNumFirst);
			numFirst = randNumFirst.getValue(max, min);
			
			
			long seedNumSecond = i + 1 + System.currentTimeMillis() ;
			RandomNum randoNumSecond = new RandomNum(seedNumSecond);
			numSecond = randoNumSecond.getValue(max, min);

			long seedSign = i + 2 + System.currentTimeMillis();
			RandomNum randSign = new RandomNum(seedSign); 
			signNum[i] = sign[randSign.getValue(3, 0)];
			if(signNum[i].equals("+")){
				
				
				result = numFirst + numSecond;
				System.out.println(numFirst + signNum[i] + numSecond + 
						"=" + result);
			}else if(signNum[i].equals("-")){
				result = numFirst - numSecond;
				System.out.println(numFirst + signNum[i] + numSecond + 
						"=" + result);
			}else if(signNum[i].equals("*")){
				result = numFirst * numSecond;
				System.out.println(numFirst + signNum[i] + numSecond + 
						"=" + result);
			}else if(signNum[i].equals("/")){
				result = numFirst / numSecond;
				System.out.println(numFirst + signNum[i] + numSecond + 
						"=" + result);
			}
		}
	}
}
package qiheng.wei.xianghua.sang;

import java.util.Random;

public class RandomNum {
	private Random rand;
	
	public RandomNum(long seed){
		rand = new Random(seed);
	}
	public int getValue(int max ,int min){
		int value = 0;
		
		value = rand.nextInt(max - min +1) + min;
		
		return value;
	}
}
