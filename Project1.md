# NewProject

# Task01
          Please implement this method to
          return the number in the array that is closest to zero.
          If there are two equally close to zero elements like 2 and -2
          - consider the positive element to be "closer" to zero.

public class BetterProgrammerTask {
    
    public static int getClosestToZero(int[] a) {
        int min = a[0];
        for (int i = 1; i <a.length ; i++) {
             if (Math.abs(a[i])<min)
                 min = Math.abs(a[i]);
        }
        return min;
    }
}

# Task02
          Please implement this method to
          return the sum of the two largest numbers in a given array.
         
public class BetterProgrammerTask {

    public static int sumOfTwoLargestElements(int[] a) {
        int max1 = a[0];
        int max2 = a[0];
        for (int i = 1; i <a.length; i++) {
            if (a[i]>max1)
                max1=a[i];
        }
        for (int i = 1; i <a.length; i++) {
            if (a[i]>max2 && a[i]!=max1)
                max2=a[i];
        }
        int sum = max1 + max2;
        return sum;
    }
}


# Task04
        You need to sort an array of integers by repeatedly reversing
        the order of the first several elements of it.

         For example, to sort [12,13,11,14], you need to  reverse the order of the first two (2)
         elements and get [13,12,11,14] and then reverse the order of the first three (3)
         elements and get [11,12,13,14]

         The method should return the shortest(!) possible list of integers corresponding to the required reversals.
         For the previous example, given an array [12,13,11,14]
         the method should return a list with Integers 2 and 3.


public class BetterProgrammerTask {

    public static List<Integer> getReversalsToSort(int[] a) {
    boolean flag = true;
        ArrayList <Integer> lst = new ArrayList<Integer>();
        for (int j = 1; j < a.length; j++) {
                for (int i = 0; i <a.length-1; i++) {
                    if (a[i]<a[i+1] && flag)
                        flag=true;
                    else
                        flag=false;
                }
                    if (flag==false){
                        int tmp = a[0];
                        a[0] = a[j];
                        a[j] = tmp;
                        lst.add(j);
                    }

                }
            return lst;
            }
    }

