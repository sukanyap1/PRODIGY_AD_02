import java.util.ArrayList;
import java.util.Calendar;
import java.util.Scanner;

public class ToDoList {
    static Scanner userInput = new Scanner(System.in);
    static ArrayList<String> userList = new ArrayList<>();

    public static void createList() {
        System.out.println("ToDoList Creator - Create to do lists using Java.");
        System.out.println("Type '!view' to exit and view your list.");
        System.out.println("Enter your tasks in the line below.");
        while (true) {
            System.out.print("-: ");
            String definedCommand = userInput.nextLine();
            SimpleDateFormat simpleDate = new SimpleDateFormat("yyyy/MM/dd");
            Calendar currentDate = Calendar.getInstance();
            if (definedCommand.equals("!view")) {
                System.out.println("List's Date: " + simpleDate.format(currentDate.getTime()));
                for (int listSize = 0; listSize != userList.size(); listSize++) { 
                    System.out.println(listSize + 1 + ". " + userList.get(listSize));
                }
                break;
            } else {
                userList.add(definedCommand);
            }
        }
    }

    public static void main(String[] args) {
        createList();
    }
}
