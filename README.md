#include <stdio.h>

int main()
{
    int k, lower, upper, mid, n, search, arr[50];

    printf("Enter size of array: ");
    scanf("%d", &n);

    printf("Enter %d elements in sorted order:\n", n);
    for(k = 0; k < n; k++)
    {
        scanf("%d", &arr[k]);
    }

    printf("Enter element you want to search: ");
    scanf("%d", &search);

    lower = 0;
    upper = n - 1;

    while(lower <= upper)
    {
        mid = (lower + upper) / 2;

        if(arr[mid] < search)
        {
            lower = mid + 1;
        }
        else if(arr[mid] == search)
        {
            printf("\n%d found at location %d\n", search, mid);
            return 0;
        }
        else
        {
            upper = mid - 1;
        }
    }

    printf("\n%d not found in the list\n", search);
    return 0;
}
