class binarysearch { 
    int binarySearch(int arr[], int l, int r, int x)
    {
        if (r >= l) {
            int mid = l + (r - l) / 2;
 
             if (arr[mid] == x)
                return mid; 
             
            if (arr[mid] > x)
                return binarySearch(arr, l, mid - 1, x);
 
         return binarySearch(arr, mid + 1, r, x);
        }
 
        return -1;
    }
 
    public static void main(String args[])
    {
        binarysearch ob = new binarysearch();
        int arr[] = { 1,10,20,30,40 };
        int n = arr.length;
        int x = 10;
        int result = ob.binarySearch(arr, 0, n - 1, x);
        if (result == -1)
            System.out.println("Number not present");
        else
            System.out.println("Element at index " + result);
    }
}
