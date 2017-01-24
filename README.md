# Summary

Method `findNeedles` compares the elements of `haystack` string and `needles` array, gathers in `countArray` array the total count of how many elements the variables have in common, then prints each common element and the total count.

# Description

`findNeedles` method accepts two arguments, `haystack` string and `needles` string array.

    public static void findNeedles(String haystack, String[] needles){

Method checks if `needles` contains more than five elements. If `needles` contains more than five elements, throw an error and print an error message. Else, if `needles` contains fewer than five elements, continue. Integer array `countArray` is instantiated with a capacity equal to the length of `needles`.

    if(needles.length > 5){
        System.err.println("Too many words!"); }
    else{
        int[] countArray = new int[needles.length];

`haystack` string is split based on a regular expression: all spaces, quotation marks `‘` `“`, tabs `\t`, newlines `\n`, word boundaries `\b`, and returns `\r` are removed. The remaining elements are stored in string array `words`.

    for(int i = 0; i < needles.length; i++){
        String[] words = haystack.split("[ \"\'\t\n\b\f\r]", 0);

Each element of `words` is compared to each element of `needles`. For each precise match, `countArray` is incremented.

    for(int j = 0; j < words.length; j++){
        if(words[j].compareTo(needles[i]) == 0){ countArray[i]++;}

Each matched element and the total number of matched elements is printed.

    for (int j = 0; j < needles.length; j++) {
        System.out.println(needles[j] + ": " + countArray[j]);
