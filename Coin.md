import java.util.Vector;
 
class coinchanging
{
    static int deno[] = {1, 5, 10};
    static int n = deno.length;
 
    static void findMin(int V)
    {
        Vector<Integer> ans = new Vector<>();
        for (int i = n - 1; i >= 0; i--)
        {
            while (V >= deno[i])
            {
                V -= deno[i];
                ans.add(deno[i]);
            }
        }
        for (int i = 0; i < ans.size(); i++)
        {
            System.out.print(
                " " + ans.elementAt(i));
        }
    }
    public static void main(String[] args)
    {
        int n = 12;
        System.out.print(
            "optimal solution "
            +"of change for " +  n + " :is ");
        findMin(n); 
    }
}
