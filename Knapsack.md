package knapsack;
class Knapsack {
 static int maximum(int a, int b) 
{ return (a > b) ? a : b; }
 static int knapSack(int W, int weight[], int value[], int n)
 {
     int i, w;
     int K[][] = new int[n + 1][W + 1];
     for (i = 0; i<= n; i++) {
         for (w = 0; w<= W; w++) {
             if (i == 0 || w == 0)
                 K[i][w] = 0;
             else if (weight[i - 1]<= w)
                 K[i][w] = maximum(value[i - 1] + K[i - 1][w - weight[i - 1]], K[i - 1][w]);
             else
                 K[i][w] = K[i - 1][w];
         }
     }

     return K[n][W];
 }
 public static void main(String args[])
 {
     int value[] = new int[] { 2, 3, 1, 4 };
     int weight[] = new int[] { 3, 4, 6, 5 };
     int capacity = 8;
     int n = value.length;
     System.out.println("Maximum profit With Respect to weight is :- " +knapSack(capacity, weight, value, n));
 }
}
