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





   practical no 10

   #include <stdio.h>

int main() {
    int arr[50], n, i, j, temp;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    printf("Enter %d elements:\n", n);
    for(i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    // Insertion Sort logic
    for(i = 1; i < n; i++) {
        temp = arr[i];
        j = i - 1;
        while(j >= 0 && arr[j] > temp) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = temp;
    }

    printf("\nSorted array in ascending order:\n");
    for(i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }

    return 0;
}
