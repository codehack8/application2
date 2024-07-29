# application2
interface EmployeeInterface {
	public void employeeInfo(int eno,float sal) throws Exception;
	public void employeeAddress(String add);	
	public void employeeDeatils();
}
abstract class BankAccountDetails {
	abstract public void accountDetails();
	
	public void bankDetails() {
		System.out.println("My Bank is ICICI ..");
	}
	

}
class BankRBI {
	
	static{
		System.out.println("Welcome to Employee Details");
	}
	
	public BankRBI() {
		System.out.println("RBI Bank Home Loan and Personal loan Interest");
	}
	public BankRBI(double p,double r) {
	   System.out.println(p*r/100);
	}

	  public static final void getBankDetails() {
		  System.out.println("Home Laon Interest in 8.5");
		  System.out.println("Personal loan Interset is 11%");
	  }
	
}
public class EmployeeInformation extends BankAccountDetails implements EmployeeInterface  {
	int empno;
	double sal;
	String address;
	
	// Interface override methods
	public void employeeInfo(int eno,float sal) throws Exception
	{
		this.empno=eno;
		this.sal=sal;
	}
	public void employeeAddress(String add) {
	 this.address = add;
	}
	public void employeeDeatils() {
		System.out.println("Employee No :"+empno);
		System.out.println("Employee Sal :"+sal);
		System.out.println("Employee Address "+address);
		
	}
	// abstract class implementation 
	public void accountDetails()
	{
		System.out.println("Myaccount details is  : 12345678");
	}
	public void show() {
		System.out.println("This is show Local method");
	}
	public static void main(String arg[]) {
		try {
			// Interface methods calling
		EmployeeInformation emp=new EmployeeInformation();
		emp.employeeInfo(100,5000);
		emp.employeeAddress("Bangalore");
		emp.employeeDeatils();
		// Abstract class
		emp.accountDetails();
		emp.bankDetails();
		
		// calling Bank RBI  with HAS-A
		BankRBI rbi=new BankRBI();
		BankRBI rbi1=new BankRBI(3.3,3.3);
		BankRBI.getBankDetails();
		
		// call local methods
		emp.show();
		}
		catch(Exception e) {
			System.out.println("I can handle "+e);
		}
	}

}
