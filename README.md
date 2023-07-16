# Anagrams
import java.util.Arrays;

public class AnagramChecker {
    public static boolean areAnagrams(String str1, String str2) {
        String cleanStr1 = str1.replaceAll("[^a-zA-Z]", "").toLowerCase();
        String cleanStr2 = str2.replaceAll("[^a-zA-Z]", "").toLowerCase();
        if (cleanStr1.length() != cleanStr2.length()) {
            return false;
        }
        char[] arr1 = cleanStr1.toCharArray();
        char[] arr2 = cleanStr2.toCharArray();
        Arrays.sort(arr1);
        Arrays.sort(arr2);
        return Arrays.equals(arr1, arr2);
    }

    public static void main(String[] args) {
        String str1 = "listen";
        String str2 = "silent";
        boolean areAnagrams = areAnagrams(str1, str2);
        System.out.println(areAnagrams); 

        str1 = "restful";
        str2 = "fluster";
        areAnagrams = areAnagrams(str1, str2);
        System.out.println(areAnagrams); 
    }
}
