public class Caesar {
    /**
     *This function is for the rotation process
     * @param shift this represents the number of positions the char should be moved
     * @param myChar this is the character that is going to be encrypted
     * @return is used to return the encrypted character
     */
    public  static char rotate(int shift, char myChar){
        char finalChar = '\0';
        if (Character.isLetter(myChar)) { //verification if it is a letter
            if (Character.isLowerCase(myChar)) { // verify if it's a lower case
                finalChar =  (char) ((( myChar - 97 + shift + 26)) % 26 + 97);
                //Shifting chars by subtracting 97 ('a') + formula
            } else if (Character.isUpperCase(myChar)) {
                //Same process here but for uppers
                finalChar =  (char) (((myChar - 65 + shift + 26) % 26) + 65);
            }
        }else{
            //Symbols
             finalChar = myChar;
        }
        return  finalChar;
    }

    /**
     *
     * @param shift This represents the number of positions the char should be moved
     * @param myString The string that is going to be encrypted
     * @return the encrypted character
     */
    public static String rotate(int shift, String myString){//this method crypts the message
        StringBuilder result = new StringBuilder();
        for(int i = 0; i < myString.length(); i++){
            char myChar = myString.charAt(i); //Chars of string
            if(Character.isLetter(myChar)) {
                result.append(rotate(shift, myChar)); // appending letters
            }else{
                result.append(myChar); //appending symbols
            }
        }
        return result.toString(); // returning the result
    }

    /**
     *
     * @param args represents the command line arguments
     *
     */
    public static void main(String[] args) {
        if(args.length != 2){
            if (args.length < 2){
                System.out.println("Too few parameters!");
            }else{
                System.out.println("Too many parameters!");
            }
            System.out.println("Usage: java Caesar n \"cipher text\"");
            return;


        }
        int shift;
        try{
             shift = Integer.parseInt(args[0]);
        }catch (NumberFormatException ex){
            System.out.println("Please enter a valid integer");
            System.out.println("Usage: java Caesar n \"cipher text\"");
            return;
        }

        String myString = args[1];
        System.out.println(rotate(shift, myString));
    }
}
