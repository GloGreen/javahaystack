# Summary

Method `findNeedles` compares the elements of `haystack` and `needles`, gathers their matching elements, then prints each matching element and the total number of matching elements.

# Description

`findNeedles` method accepts two arguments, `haystack` string and `needles` string array.

    public static void findNeedles(String haystack, String[] needles){

Method checks if `needles` contains more than five elements. If `needles` contains more than five elements, an error occurs and an error message is printed. Otherwise, if `needles` contains fewer than five elements, and integer array `countArray` is instantiated with a capacity equal to the length of `needles`.

    if(needles.length > 5){
        System.err.println("Too many words!"); }
    else{
        int[] countArray = new int[needles.length];

`haystack` string is split based on a regular expression: all spaces, quotation marks `‘` `“`, tab characters `\t`, line feeds `\n`, word boundaries `\b`, form feeds `\f`, and carriage returns `\r` are removed. The remaining elements are stored in `words` string array.

    for(int i = 0; i < needles.length; i++){
        String[] words = haystack.split("[ \"\'\t\n\b\f\r]", 0);

Each element of `words` is compared to each element of `needles`. For each precise match, `countArray` is incremented.

    for(int j = 0; j < words.length; j++){
        if(words[j].compareTo(needles[i]) == 0){ countArray[i]++;}

Each matched element and the total number of matched elements is printed.

    for (int j = 0; j < needles.length; j++) {
        System.out.println(needles[j] + ": " + countArray[j]);
