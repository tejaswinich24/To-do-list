//TO-DO LIST

#include<iostream>
#include<string.h>

using namespace std;

class TDL
{
	public:	

		int count=0;		
		string task[30];

		void insert(int k)
		{
			cout<<"Enter "<<k<<" tasks:\n";
			for(int i=0; i<k; i++)
			{
				cin>>task[count++];	
			}
		}

		void add(int n)
		{
			cout<<"Add more tasks:\n";
			for(int i=0; i<n; i++)
			{
				cin>>task[count++];			
			}
			cout<<"Tasks added!";
		}

		void view()
		{
			cout<<"\nYour entered tasks are:\n";
			for(int i = 0; i< count; i++)
			{
				cout<<"Task "<<i+1<<": "<< task[i] <<endl;
			}
		}

		void comp(int n)
		{
			task[n-1].append("-->Completed");
		}

		void remove(int n)
		{
    		if (n < 1 || n > count)
    		{
        		cout << "Invalid task number" << endl;
        		return;
    		}

    		for (int i = n - 1; i < count - 1; i++)
    		{
        		task[i] = task[i + 1];
    		}
   			count--;
		}

};

int main()
{
	TDL l1;
	int n,ch;
	char ans = 'y';
	do
	{
		cout<<"\t\t# TO-DO LIST #";
		cout<<"\n1.Task Input\n2.Add Task\n3.View Tasks\n4.Mark task as Completed\n5.Remove task";
		cout<<"\nEnter your choice: ";
		cin>>ch;
		switch(ch)
		{
			case 1: 
				cout<<"Enter no. of tasks: ";
				cin>>n;
				l1.insert(n);
				break;

			case 2:
				cout<<"Enter no. of tasks to be added: ";
				cin>>n;
				l1.add(n);
				l1.view();
				break;
			
			case 3:
				l1.view();
				break;
			
			case 4:
				cout<<"Which task no.? ";
				cin>>n;
				l1.comp(n);
				l1.view();
				break;
			
			case 5:
				cout<<"Enter task no. to be deleted: ";
				cin>>n;
				l1.remove(n);
				l1.view();
				break;
		}
		cout<<"Do you want to continue? (enter y/n) ";
		cin>> ans;
		
    }while(ans=='y' || ans== 'Y');
	return 0;
}
