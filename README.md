// publication


package book;

import java.util.Scanner;



class Publication {

    int copies;

    String title;

    float price;

    

    void accept() {

        Scanner sc = new Scanner(System.in);

        System.out.println("Enter title:");

        title = sc.nextLine();

        System.out.println("Enter no of copies:");

        copies = sc.nextInt();

        System.out.println("Enter price:");

        price = sc.nextFloat();

    }



    void display() {

        System.out.println("Title: " + title);

        System.out.println("Price: " + price);

        System.out.println("No of copies: " + copies);

    }

    void sale_copies() {

    	float  total_sale,st0ck;

    	int ci;

    	Scanner sc = new Scanner(System.in);

    	

    	System.out.println("Enter no. of copies issued: ");

    	ci=sc.nextInt();

    	total_sale=ci*this.price;



    	st0ck=this.copies-ci;

    	System.out.println("stock remaining:"+st0ck);

    	System.out.println("The total sale of publication is :"+ci+"copies");

    }

}



class Book extends Publication {

    private String author;



    void ordercopies() {

        Scanner sr = new Scanner(System.in);

        System.out.println("Enter author name:");

        author = sr.nextLine();

    }

    void display_author(){

    	System.out.println(this.author);

    }

}



class   Magzine extends Book {

    int quantity;

    

    void receive_issue(String new_issue_date) {		

		//method to issue new or upgraded magazine

    	Scanner sc = new Scanner(System.in);

		System.out.println("ENTER NEW COPIES ORDERED: ");

		quantity=sc.nextInt();			

	

		

	

		System.out.println("\tTHE MAGAZINE "+this.title +" "+"AVAILABLE");}

    void orderquantity() {

        Scanner sc = new Scanner(System.in);

        System.out.println("Enter no. of copies to be ordered:");

        quantity = sc.nextInt(); 

    }



    void currentissue() {

        System.out.println("Currently issued book: " + super.title);

    }



    void recieveissue() {

        System.out.println("Received issued book: " + super.title);

        System.out.println("No. of copies ordered are: " + this.quantity);

    }

}



class main {

    public static void main(String[] args) {




          Publication p=new Publication();

          Book b=new Book();

          Magzine m=new Magzine();

          Scanner sc=new Scanner(System.in);




    	

          int outer;	

      	do {

      		

      			System.out.println("\n\n\tCHOOSE ONE OF THE FOLLOWING....\n\n\t1.BOOK \t\t\t2.MAGAZINE"

      					);

      			System.out.print("Choice::");

      			int k=sc.nextInt();

      			int a;

      			aa:

      				

      			if(k==1) {

      				float  ci,total_sale,stock;

      				

      				do {

      				int c;

      				System.out.print("\n\t\tMENU   FOR   BOOK\n");

      				System.out.println("\t1.read book \t\t2.display \n\t3.sale copies \t");

      				System.out.print("\n\tChoice::");

      				c=sc.nextInt();

      				switch (c){

      				

      				case 1:

      					System.out.println("==============================================================================\n");

      					b.accept();

      					System.out.println("==============================================================================\n");

      					break;

      				case 2:

      					System.out.println("==============================================================================\n");

      					b.display();

      					System.out.println("==============================================================================\n");

      					break;

      				case 3:

      					System.out.println("==============================================================================\n");

      					b.sale_copies();

      					System.out.println("==============================================================================\n");

      					break;

      				

      				default:

      					System.out.println("invalid");

      					

      				}

      				System.out.println("Do you want to continue with book section[1/0]\n\t1.YES \t\t0.NO");

      				System.out.print("\tChoice::");

      				a=sc.nextInt();

      				if(a==0)

      					 break aa;

      			

      			}while(a==1);

      				

      			}

      			

      			else if(k==2)

      			{

      				

      				

      				mm:

      				do {

      				System.out.println("\n\t\tMENU   FOR   MAGAZINE...\n\n\t1.read magzine\n\t2.currentIssue\n\t3.Sale of magzine\n\t4.recieve_issue");

      				int d;

      				System.out.print("\n\tChoice::");

      				d=sc.nextInt();

      				switch(d) {

      				case 1:

      					System.out.println("==============================================================================\n");

      					m.accept();

      					System.out.println("==============================================================================\n");

      					break;

      				case 2:

      					System.out.println("==============================================================================\n");

      					m.display();

      					System.out.println("==============================================================================\n");

      					break;

      				case 3:

      					System.out.println("==============================================================================\n");

      					m.sale_copies();

      					System.out.println("==============================================================================\n");

      					break;

      				case 4:

      					System.out.println("==============================================================================\n");

      					System.out.println("ENTER THE NEW ISSUE DATE [dd/mm/yyyy]: ");

      					String date=sc.next();

      					m.receive_issue(date);

      					System.out.println("==============================================================================\n");

      					break;

      				}

      				System.out.println("DO YOU WANT TO CONTINUE WITH MAGAZINE SECTION [1/0]\n\t1.YES\t0.NO");

      				System.out.print("\tChoice::");

      				a=sc.nextInt();

      				if(a==0)

      					break mm;

      				

      			}while(a==1);

      			}

      			

      			

      			else

      				System.out.println("invalid key....");

      			System.out.println("DO YOU WANT TO CONTINUE WITH PUBLICATION???\n\t1.CONTINUE \t0.TERMINATE");

      			outer=sc.nextInt();

      	}while(outer!=0);System.out.println("DO YOU WANT TO CONTINUE WITH PUBLICATION???\n\t1.CONTINUE \t0.TERMINATE");

			outer=sc.nextInt();

      	sc.close();

      	}

      }



