public class Brutus {
    /**
     * english alphabet frequency
     */
    public static final double[] english = {
            0.0855, 0.0160, 0.0316, 0.0387, 0.1210, 0.0218, 0.0209, 0.0496, 0.0733,
            0.0022, 0.0081, 0.0421, 0.0253, 0.0717, 0.0747, 0.0207, 0.0010, 0.0633,
            0.0673, 0.0894, 0.0268, 0.0106, 0.0183, 0.0019, 0.0172, 0.0011
    };

    /**
     * This function counts the frequency of each letter
     * @param myString represents the string that we need to analyze
     * @return This returns an array which contains the frequency of each letter in out string (myString)
     */
    public static int[] count(String myString) {
        myString = myString.toLowerCase();
        int[] myStringFreq = new int[26];
        for (int i = 0; i < myString.length(); i++) {
            char currentChar = myString.charAt(i);
            if (Character.isLetter(currentChar)) {
                myStringFreq[currentChar - 97]++;
            }

        }
        return myStringFreq;
    }

    /**
     *
     * @param myString represents the string that we need to analyze
     * @return This function returns the frequency of each letter but sorted in alphabetical order
     */

    public static double[] frequency(String myString) {
        double[] letterFrequency = new double[26];
        int[] myStringFrequency = count(myString);
        for (int i = 0; i < letterFrequency.length; i++) {
        letterFrequency[i] = (double) myStringFrequency[i] / myString.length();
        }
        return letterFrequency;
    }

    /**
     *
     * @param frqOne This is our first set of frequencies that we are using
     * @param frqTwo This is our second set of frequencies that we are using
     * @return This will return the chiSquared value which is going to indicate us similarities of the distribution
     */
    public static double chiSquared(double[] frqOne, double[] frqTwo) {
        double chiSquaredValue = 0;
        for (int i = 0; i < 26; i++) {
            double diffSquared = Math.pow((frqOne[i] - frqTwo[i]), 2);
            chiSquaredValue = chiSquaredValue + diffSquared / english[i];
        }
        return chiSquaredValue;
    }

    /**
     *
     * @param args user input as command line
     * Here we have method implementation
     * In the main we are decrypting the string and print it for the user
     */
    public static void main(String[] args) {
        //checking args
        if (args.length < 1) {
            System.out.println("Too few parameters!");
            System.out.println("Usage: java Brutus \"cipher text\"");
            return;
        } else if (args.length > 1) {
            System.out.println("Too many parameters!");
            System.out.println("Usage: java Brutus \"cipher text\"");
            return;
        }

        String textToDecrypt = args[0];
        String closestDecryption = "";
        double minChiSquared = 9999999;

        for (int i = 0; i < 26; i++) {
            String decryptedTxt = Caesar.rotate(i, textToDecrypt);

            double[] frequencyOfDecrypted = frequency(decryptedTxt);
            double valueOfChiSquared = chiSquared(frequencyOfDecrypted, english);

            if (valueOfChiSquared < minChiSquared) {
                minChiSquared = valueOfChiSquared;
                closestDecryption = decryptedTxt;
            }

        }
        System.out.println(closestDecryption);
    }
}
