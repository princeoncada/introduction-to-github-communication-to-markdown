# This is an h1 header
## This is an h2 header
### This is an h3 header
#### This is an h4 header
##### This is an h5 header
###### This is an h6 header

![Image Test](https://image.shutterstock.com/image-vector/art-deco-trellis-lines-seamless-600w-1713206362.jpg)

```
public class SortingAlgorithm_OncadaTest {
    public static int num = 1;
    public String all = "";
    public double arr[];

    SortingAlgorithm_OncadaTest(double arr[]){
        this.arr = arr;
    }

    public boolean stateChecker(double num1, double num2, int order) {
        if (order == 0) {
            return num1 > num2;
        }return num2 > num1;
    }
    public boolean stateCheckerQ(double num1, double num2, int order) {
        if (order == 0) {
            return num1 > num2;
        }return num2 >= num1;
    }

    public void swap(double arr[], int i, int j) {
        double hold = arr[i];
        arr[i] = arr[j];
        arr[j] = hold;
    }

    public int partition(double arr[], int low, int high, int order) {

        int pivot = (int) arr[high];
        int i = (low - 1);

        for(int j = low; j <= high-1; j++) {
            if(stateCheckerQ(pivot, arr[j], order)) {
                i++;
                swap(arr, i, j);
            }
        }
        swap(arr, i+1, high);
        return (i + 1);
    }

    public String stringArray(double[] arr)
    {
        this.all += "Iteration #"+(num)+": ";
        for(double x:arr){
            this.all += (int)x + " ";
        }this.all += "\n";
        return this.all;
    }

    public void quickSort(double[] arr, int low, int high, int order) {
        if(low < high) {
            stringArray(arr);
            num += 1;
            int mid = partition(arr, low, high, order);
            quickSort(arr, low, mid - 1, order);
            quickSort(arr, mid + 1, high, order);
        }
    }

    public String bubbleSort(int order){

        String all = "";
        double hold = 0;
        double[] new_arr = this.arr.clone();

        long start = System.nanoTime();
        all += "Bubble Sort Algorithm\n";

        for(int i=0;i<new_arr.length;i++){

            all += "Iteration #"+(i+1)+": ";
            for(double x:new_arr){
                all += (int)x + " ";
            }all += "\n";

            for(int j=0;j<new_arr.length-1;j++){
                if(stateChecker(new_arr[j], new_arr[j+1], order)){
                    hold = new_arr[j+1];
                    new_arr[j+1] = new_arr[j];
                    new_arr[j] = hold;
                }
            }
        }

        long end = System.nanoTime();
        all += "Processing Time\t: "+(end-start)+" units.";
        return all;
    }

    public String selectionSort(int order){

        String all = "";
        double hold = 0;
        double[] new_arr = this.arr.clone();
        int index = 0;

        long start = System.nanoTime();
        all += "Selection Sort Algorithm\n";

        for(int i=0;i<new_arr.length;i++){
            index = i;

            all += "Iteration #"+(i+1)+": ";
            for(double x:new_arr){
                all += (int)x + " ";
            }all += "\n";

            for(int j=i+1;j<new_arr.length;j++){
                if (stateChecker(new_arr[index], new_arr[j], order)) {
                    index = j;
                }
            }
            hold = new_arr[index];
            new_arr[index] = new_arr[i];
            new_arr[i] = hold;
        }

        long end = System.nanoTime();
        all += "Processing Time\t: "+(end-start)+" units.";
        return all;
    }

    public String exchangeSort(int order){

        String all = "";
        double hold = 0;
        double[] new_arr = this.arr.clone();

        long start = System.nanoTime();
        all += "Exchange Sort Algorithm\n";

        for(int i=0; i<new_arr.length; i++){

            all += "Iteration #"+(i+1)+": ";
            for(double x:new_arr){
                all += (int)x + " ";
            }all += "\n";

            for(int j=i+1;j<new_arr.length;j++){
                if(stateChecker(new_arr[i], new_arr[j], order)){
                    hold = new_arr[i];
                    new_arr[i] = new_arr[j];
                    new_arr[j] = hold;
                }
            }
        }

        long end = System.nanoTime();
        all += "Processing Time\t: "+(end-start)+" units.";
        return all;
    }

    public String insertionSort(int order){

        String all = "";
        double[] new_arr = this.arr.clone();

        long start = System.nanoTime();

        all += "Insertion Sort Algorithm\n";
        for(int i=1; i<new_arr.length; i++){
            double current = new_arr[i];
            int j = i-1;
            while(j >= 0 && stateChecker(new_arr[j], current, order)){
                new_arr[j+1] = new_arr[j];
                j--;
            }
            new_arr[j+1] = current;

            all += "Iteration #"+(i)+": ";
            for(double x:new_arr){
                all += (int)x + " ";
            }all += "\n";

        }

        long end = System.nanoTime();
        all += "Processing Time\t: "+(end-start)+" units.";
        return all;
    }

    public String quickSort(int order){
        double[] new_arr = this.arr.clone();
        int low = 0, high = new_arr.length-1;

        long start = System.nanoTime();
        this.all += "\nQuick Sort Algorithm\n";
        quickSort(new_arr, low, high, order);
        stringArray(new_arr);
        long end = System.nanoTime();

        this.all += "Processing Time\t: "+(end-start)+" units.";
        return this.all;
    }
}

```

