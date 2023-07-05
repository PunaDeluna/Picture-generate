# Picture-generate
Picture
public class WordPictureGenerator {
    public static void main(String[] args) {
        String word = "WORD"; // The word to generate the picture
        int size = 5; // The size of the picture

        // Generate the word picture
        String[][] picture = generateWordPicture(word, size);

        // Print the word picture
        for (String[] row : picture) {
            for (String letter : row) {
                System.out.print(letter);
            }
            System.out.println();
        }
    }

    public static String[][] generateWordPicture(String word, int size) {
        int length = word.length();
        String[][] picture = new String[size][length * size];

        // Fill the picture array with spaces
        for (int i = 0; i < size; i++) {
            for (int j = 0; j < length * size; j++) {
                picture[i][j] = " ";
            }
        }

        // Place the letters of the word in the picture array
        for (int i = 0; i < length; i++) {
            char letter = word.charAt(i);
            int column = i * size + size / 2;

            for (int j = 0; j < size; j++) {
                int row = j;

                if (j >= size / 2) {
                    row = size - j - 1;
                }

                picture[row][column] = String.valueOf(letter);
            }
        }

        return picture;
    }
}
