# talarir
#include<stdio.h>
#include<stdlib.h>

int main()
{
	int Elements = 0;
	int *arr = NULL;
	int index = 0;
	int temp = 0;
	int inner_loop = 0;
	printf("\n Enter a number of elements : ");
	scanf("%d", &Elements);
	arr = malloc(sizeof(int)*Elements);
	for(index = 0; index<Elements; index++)
	{
		printf("\n Please enter element(%d) of array : ", index);
		scanf("%d", &arr[index]);
	}
	printf("\n Given array is [");
	for(index = 0; index<Elements-1; index++)
	{
		printf("%d, ", arr[index]);
	}
	printf("%d]", arr[index]);
	
	
	for(index = 1; index< Elements; index++)
	{
		inner_loop = index - 1;
		temp = arr[index];
		while(inner_loop >=0 && (arr[inner_loop] > temp))
		{
			arr[inner_loop + 1] = arr[inner_loop];
			inner_loop = inner_loop -1;
		}
		arr[inner_loop + 1] = temp;
	}


	printf("\n Sorted array is [");
	for(index = 0; index<Elements-1; index++)
	{
		printf("%d, ", arr[index]);
	}
	printf("%d]\n", arr[index]);

	
	return 0;
}
