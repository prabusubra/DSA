```
public class ArrayExamples {

	public static void main(String[] args) {
		int[] arr = {3,6,-18,9,15,7,8, 10, 15};
		//int[] arr = {10,10,10,10};
		int[] arr1 = {1,2,3,4,5};
		System.out.println("Largest Element : "+arr[getLargestElement(arr)]);
		System.out.println("2nd Largest Element : "+getSecondLargestElement(arr));
		System.out.println("2nd Largest Element : "+arr[getSecondLargestElement(arr)]);
		System.out.println("2nd Largest Element : "+getSecondLargestElementv1(arr));
		System.out.println("2nd Largest Element : "+arr[getSecondLargestElementv1(arr)]);
		System.out.println("sorted : "+isSorted(arr));
		
		System.out.println("sorted : "+isSorted(arr1));
		System.out.println("sorted : "+isSortedV1(arr));
		System.out.println("sorted : "+isSortedV1(arr1));
	}
	static int getLargestElement(int[] arr) {
		int result = 0;
		for (int i=0; i < arr.length; i++) {
			if (arr[i] > arr[result]) {
				result = i;
			}
		}
		return result;
	}
	
	static int getSecondLargestElement(int[] arr) {
		int zero = 0, one = 0, flag = 0;
		
		for (int i=0; i < arr.length; i++) {
			if (arr[i] > arr[one]) {
				flag = 1;
				zero = one;
				one = i;
			} else if (arr[i] > arr[zero] && arr[i]!=arr[one]) {
				flag = 1;
				zero = i;
			}
		}
		
		return flag ==1 ? zero: -1;
	}
	
	static int getSecondLargestElementv1(int[] arr) {
		int zero = -1, one = 0;
		
		for (int i=0; i < arr.length; i++) {
			if (arr[i] > arr[one]) {
				zero = one;
				one = i;
			} else if (arr[i]!=arr[one]) {
				if (zero == -1 || arr[i] > arr[zero]) {
					zero = i;
				}
				
			}
		}
		return zero;
	}
	static boolean isSorted(int[] arr) {
		int last = 0;
		for (int i = 1; i < arr.length;i++) {
			if (arr[last] > arr[i]) {
				return false;
			} else {
				last++;
			}
		}
		return true;
	}
	
	static boolean isSortedV1(int[] arr) {
		for (int i = 1; i < arr.length;i++) {
			if (arr[i-1] > arr[i]) {
				return false;
			} 
		}
		return true;
	}
	
}

static int[] reverse(int[] arr) {
		for (int left=0, right = arr.length-1; left < right; left++, right--) {
			int temp = arr[left];
			arr[left] = arr[right];
			arr[right] = temp;
		}
		
		return arr;
}
```
