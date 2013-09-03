akaedu-c-learn
==============

My c learn 
##www.codepad.org  在线编译

  * git clone 
  * git pull
  * git push
  * git config
  * git add
  * git commit -a -m "modify" readme



	##quick_sort.c
  
        #include <stdio.h>
        #include <stdlib.h>
        
        #define N	16
        #define MAX	100
        
        void init_arry(int a[], int len)
        {
        	int i;
        	srand(time(NULL));
        	for(i = 0; i < len; i++)
        		a[i] = rand() % MAX;
        }
        
        void show(int a[], int len)
        {
        	int i;
        	for(i = 0; i < len; i++)
        		printf("%3d", a[i]);
        	putchar('\n');
        }
        
        void swap(int *a, int *b)
        {
        	int tmp;
        	tmp = *a;
        	*a = *b;
        	*b = tmp;
        }
        
        int partition(int a[], int start, int end)
        {
        	 int i, tmp;
        	
        	 for(i = start+1, tmp = start; i <= end; i++)
        		 if(a[i] < a[start])
        			 swap(&a[i], &a[++tmp]);
        	 swap(&a[tmp], &a[start]);
        	 return tmp;
        }
        
        void quick_sort(int a[], int start, int end)
        {
        	int m;
        	
        	if(start >= end)
        		return;
        	m = partition(a, start, end);
        	quick_sort(a, start, m-1);
        	quick_sort(a, m+1, end);
        }
        
        int main(void)
        {
        	int a[N];
        	int start = 0;
        	int end = N - 1;
        	
        	init_arry(a, N);
        	show(a, N);
        	
        	quick_sort(a, start, end);
        	show(a, N);
        
            return 0;
         }
	##quick_sort 思想是找到a[start]或者a[i]的实际位子， 并把比他小的移到他前面，比他大的移到后面，递归完成所有。
