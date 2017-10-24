import java.util.ArrayList;
import java.util.Scanner;
public class TrackScore {

	private String name;
	private int age;
	private int events;
	private int rank;
	private ArrayList<Integer>[] times;
	private Scanner input = new Scanner(System.in);
	public TrackScore(String nm, int a, int e, int r) {
		name = nm;
		age = a;
		events = e;
		rank = r;
		times = new ArrayList[e];
		for(int k=0;k<e;k++) {
			System.out.println("Enter the times for each event in order.");;
			times[k].add(input.nextInt());
		}
	}
	
	public String getName(){
		return name;
	}
	public int getAge() {
		return age;
	}
	public int getEvents() {
		return events;
	}
	public int getRank() {
		return rank;
	}
	public String getTimes() {
		String timeout = "";
		for(int k = 0; k< times.length; k++) {
			timeout += "Event " + (k+1) +": " + times[k].get(times[k].size()) +" ";
		}		
		return timeout;
	}
	public void improvement(int t, int e) {
		times[e].add(times[e].get(times[e].size())-t);
	}
	public void gain(int t, int e) {
		times[e].add(times[e].get(times[e].size())+t);
	}
	public void isVarsity() {
		if(rank < 10) {
			System.out.println("yeah, this guy's in varsity.");
		}
		else {
			System.out.println("no, hes not in varsity.");
		}
	}
	public String toString() {
		return "Name: "+ name + " Age: " + age + " Events Participated: " + times.length + " Rank: " + rank + " Average Times for each event: " + 
	}
	public int Average(int e) {
		int n = 0;
		for(int k=0; k<times[e].size(); k++) {
			n+= times[e].get(k);
		}
		return n/times[e].size();
	}
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
}
