
//TITLE:Design and implement algorithm for the Knapsack problem.

//CODE:


#include <iostream>

using namespace std;
void mergesort(double [],double [],double [],int,int);
void merge(double[],double[],double[],int,int);
int main() {
	int i,n,m;
	cout<<"\nEnter the number of items\n";
	cin>>n;
	double weight[n],profit[n],ratio[n],wt=0,ans=0;

	cout<<"Enter the weight of the items\n";
	for(i=0;i<n;i++)
	{
		cin>>weight[i];
	}

	cout<<"Enter the profit of the items\n";
	for(i=0;i<n;i++)
		{
			cin>>profit[i];
		}
	cout<<"\nEnter the maximum weight that can be taken\n";
	cin>>m;
	for(i=0;i<n;i++)
	{
		ratio[i]=profit[i]/weight[i];
	}

	mergesort(ratio,weight,profit,0,n-1);

	for(i=0;i<n;i++)
	{
		ratio[i]=0;
	}

	for(i=0;i<n;i++)
	{
		if(wt+weight[i]<m)
		{
			ratio[i]=1;
			wt=wt+weight[i];
		}
		else
		{
			if(wt!=m)
			{
			ratio[i]=(m-wt)/weight[i];
			wt=m;
			}
			else
			{
				ratio[i]=0;
			}
		}
	}
	cout<<"\nThe instances used in fractional Knapsack are\n\n";
	cout<<"Weight\t\t";
	for(i=0;i<n;i++)
		{
			cout<<weight[i]<<"\t";

		}
	cout<<"\nProfit\t\t";
	for(i=0;i<n;i++)
		{
			cout<<profit[i]<<"\t";

		}
	cout<<"\nInstance\t";
	for(i=0;i<n;i++)
	{
		cout<<ratio[i]<<"\t";
		ans=ans+(profit[i]*ratio[i]);
	}

cout<<"\n\nThe maximum profit is "<<ans;

ans=0;
cout<<"\nThe instances used in 0-1 Knapsack are\n\n";
	cout<<"Weight\t\t";
	for(i=0;i<n;i++)
		{
			cout<<weight[i]<<"\t";

		}
	cout<<"\nProfit\t\t";
	for(i=0;i<n;i++)
		{
			cout<<profit[i]<<"\t";

		}
	cout<<"\nInstance\t";
	for(i=0;i<n;i++)
	{
		if(ratio[i]==1 || ratio[i]==0)
		{
		cout<<ratio[i]<<"\t";
		ans=ans+(profit[i]*ratio[i]);

		}
		else
		{
			cout<<"0\t";
			ans=ans+(profit[i]*0);

		}
	}

cout<<"\n\nThe maximum profit is "<<ans;


return 0;

}



void mergesort(double ratio[],double weight[],double profit[],int l, int h)
{
  if(h>l)
  {
    mergesort(ratio,weight,profit,l,(l+h)/2);
    mergesort(ratio,weight,profit,((l+h)/2)+1,h);
    merge(ratio,weight,profit,l,h);
  }
}

void merge(double ratio[],double weight[],double profit[], int l, int h)
{
    int b[h],a[h],c[h];
    int i,j,m,k=l;
    i=l;
    j=((l+h)/2)+1;
    m=j-1;
    while (i<=m && j<=h)
    {
      if(ratio[i]>ratio[j])
      {
        b[k]=ratio[i];
        a[k]=weight[i];
        c[k]=profit[i];
        i++;
      }
      else
      {
        b[k]=ratio[j];
        a[k]=weight[j];
        c[k]=profit[j];
        j++;
      }
      k++;
    }

    if(i>m)
    {
      while(j<=h)
      {
        b[k]=ratio[j];
        a[k]=weight[j];
        c[k]=profit[j];
        j++;
        k++;
      }
    }
    else
    {
      while(i<=m)
      {
        b[k]=ratio[i];
        a[k]=weight[i];
        c[k]=profit[i];
        i++;
        k++;
      }
    }
    k=l;
    while(k<=h)
    {
      ratio[k]=b[k];
      weight[k]=a[k];
      profit[k]=c[k];
      k++;
    }

}



//OUTPUT:


Enter the number of items
3
Enter the weight of the items
10
20
30
Enter the profit of the items
60
100
120

Enter the maximum weight that can be taken
50

The instances used in fractional Knapsack are

Weight		10	20	30	
Profit		60	100	120	
Instance	1	1	0.666667	

The maximum profit is 240
The instances used in 0-1 Knapsack are

Weight		10	20	30	
Profit		60	100	120	
Instance	1	1	0	

The maximum profit is 160
