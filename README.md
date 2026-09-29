# Community-Development-Project
# import java.util.ArrayList;
import java.util.Scanner;

//Community participant class
class Participant {

    private int id;
    private String name;
    private int age;
    private String contact;
    private String digitalSkillLevel;
    private boolean cyberSafetyAware;

    // constructor
    public Participant(int id, String name, int age, String contact, String digitalSkillLevel, boolean cyberSafetyAware) {
        this.id = id;
        this.name = name;
        this.age = age;
        this.contact = contact;
        this.digitalSkillLevel = digitalSkillLevel;
        this.cyberSafetyAware = cyberSafetyAware;
    }

    // getters
    public int getId() {

        return id;
    }

    public String getName() {

        return name;
    }

    public int getAge() {

        return age;
    }

    public String getContact() {

        return contact;
    }

    public String getDigitalSkillLevel() {

       return digitalSkillLevel;
    }

    public boolean isCyberSafetyAware() {
        return cyberSafetyAware;
    }

    //setters
    public void setName(String name) {

        this.name = name;
    }

    public void setAge(int age) {

        this.age = age;
    }

    public void setContact(String contact) {

        this.contact = contact;
    }

    public void setDigitalSkillLevel(String digitalSkillLevel) {

        this.digitalSkillLevel = digitalSkillLevel;
    }

    public void setCyberSafetyAware(boolean cyberSafetyAware) {

        this.cyberSafetyAware = cyberSafetyAware;
    }


    //display participants information
    public void displayParticipants() {
        System.out.println("--------------------");
        System.out.println("ID  : " + id);
        System.out.println("Name  : " + name);
        System.out.println("Age  : " + age);
        System.out.println("Contact  : " + contact);
        System.out.println("DigitalSkillLevel  : " + digitalSkillLevel);
        System.out.println("CyberSafetyAware  : " + (cyberSafetyAware ? "Yes" : "No"));
        System.out.println("--------------------");
    }
}

//Main community development System
public class CommunityDevelopmentProject {
    static ArrayList<Participant>participants = new ArrayList<>();
    static Scanner sc = new Scanner(System.in);

    //add participant
    public static void addParticipant() {
        System.out.println("/n==== ADD COMMUNITY PARTICIPANT ======");

        System.out.print("Enter participant ID : ");
        int id = sc.nextInt();
        sc.nextLine();

        //Check duplicate ID
        for(Participant participant : participants) {
            if(participant.getId() == id) {
                System.out.println("Participant ID already exists");
                return;
            }
        }

        System.out.print("Enter Name: ");
        String name = sc.nextLine();

        System.out.print("Enter Age: ");
        int age = sc.nextInt();
        sc.nextLine();

        System.out.print("Enter Contact Number: ");
        String contact = sc.nextLine();

        System.out.print("Enter Digital Skill Level (Beginner/Intermediate/Advanced): ");
        String digitalSkillLevel = sc.nextLine();

        System.out.print("Is the participant aware of cyber safety (Yes/No): ");
        String answer = sc.nextLine();

        boolean cyberSafetyAware = answer.equalsIgnoreCase("Yes");

        Participant participant = new Participant(id, name, age, contact, digitalSkillLevel, cyberSafetyAware);

        participants.add(participant);

        System.out.println("\nParticipant added successfully!");
    }

    //view Participant
    public static void viewParticipant() {
        System.out.println("\n===== COMMUNITY PARTICIPANT =====");
        if(participants.isEmpty()) {
            System.out.println("No participant registered");
            return;
        }

        for(Participant participant : participants) {
            participant.displayParticipants();
        }
    }

    //search participant
    public static void searchParticipant() {
        System.out.println("\n===== SEARCH PARTICIPANT =====");
        System.out.print("Enter Participant ID: ");
        int id = sc.nextInt();

        for(Participant participant : participants) {
            if(participant.getId() == id) {
                System.out.println("\nParticipant Found!");
                participant.displayParticipants();
                return;
            }
        }

        System.out.println("Participant not found");
    }

    //Update Participant
    public static void updateParticipant() {
        System.out.println("\n===== UPDATE PARTICIPANT =====");
        System.out.print("Enter Participant ID: ");
        int id = sc.nextInt();
        sc.nextLine();

        for(Participant participant : participants) {
            if(participant.getId() == id) {
                System.out.print("Enter New Name: ");
                String name = sc.nextLine();

                System.out.print("Enter New Age: ");
                int age = sc.nextInt();
                sc.nextLine();

                System.out.print("Enter New Contact: ");
                String contact = sc.nextLine();

                System.out.print("Enter New Digital Skill Level: ");
                String digitalSkillLevel = sc.nextLine();

                System.out.print("Is the participant now aware of cyber safety (Yes/No: ");
                String answer = sc.nextLine();

                boolean cyberSafetyAware = answer.equalsIgnoreCase("Yes");

                participant.setName(name);

                participant.setAge(age);

                participant.setContact(contact);

                participant.setDigitalSkillLevel(digitalSkillLevel);

                participant.setCyberSafetyAware(cyberSafetyAware);

                System.out.println("\nParticipant updated successfully!");
                return;
            }
        }
        System.out.println("Participant not found.");
    }

    //Delete Participant
    public static void deleteParticipant() {

        System.out.println("\n===== DELETE PARTICIPANT =====");

        System.out.print("Enter Participant ID: ");
        int id = sc.nextInt();

        for(Participant participant : participants) {
            if(participant.getId() == id) {
                participants.remove(participant);

                System.out.println("Participant delete successfully!");
                return;
            }
        }
        System.out.println("Participant not found.");
    }

    //cyber safety tips
    public static void cyberSafetyTips() {
        System.out.println("\n===========================");
        System.out.println("CYBER SAFETY AWARENESS TIPS");
        System.out.println("============================");
        System.out.println("1. Use strong and unique password.");
        System.out.println("2. Never share OTPs or passwords with anyone.");
        System.out.println("3. Do not click suspicious links.");
        System.out.println("4. Verify message before sending money.");
        System.out.println("5. Enable two-factor authentication.");
        System.out.println("6. Avoid sharing personal information online.");
        System.out.println("7. Keep your phone and application updated.");
        System.out.println("8. Do not use unknown WI-FI for banking.");
        System.out.println("9. Be careful of fake job and lottery scams.");
        System.out.println("10. Report suspicious cyber activity.");
        System.out.println("==============================");
    }

    //Digital literacy Tips
    public static void digitalLiteracyTips() {
        System.out.println("\n==============================");
        System.out.println("DIGITAL LITERACY TIPS");
        System.out.println("================================");
        System.out.println("1. Learn how to use smartphone safely.");
        System.out.println("2. learn basic internet browsing.");
        System.out.println("3. Learn how to send emails.");
        System.out.println("4. Learn how to use digital payments safely.");
        System.out.println("5. Check information before sharing it.");
        System.out.println("6. Learn how to identify fake websites");
        System.out.println("7. Keep important documents backed up.");
        System.out.println("8. Learn basic privacy settings.");
        System.out.println("==================================");
    }

    //Main Method
    public static void main(String[] args) {
        while(true) {
            System.out.println("\n===============================");
            System.out.println("COMMUNITY DIGITAL LITERACY & CYBER SAFETY");
            System.out.println("=================================");
            System.out.println("1. Add Community Participant");
            System.out.println("2. View Participant");
            System.out.println("3. Search Participant");
            System.out.println("4. Update Participant");
            System.out.println("5. Delete Participant");
            System.out.println("6. Cyber Safety Tips");
            System.out.println("7. Digital Literacy Tips");
            System.out.println("8. Exit");

            System.out.println("\nEnter your choice: ");
            int choice = sc.nextInt();
            switch(choice) {

                case 1: addParticipant();
                break;

                case 2: viewParticipant();
                break;

                case 3: searchParticipant();
                break;

                case 4: updateParticipant();
                break;

                case 5: deleteParticipant();
                break;

                case 6: cyberSafetyTips();
                break;

                case 7: digitalLiteracyTips();
                break;

                case 8: System.out.println("Thank you for participating in the community development program!");
                sc.close();
                return;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
    }
}
The participant information displayed in the software demonstration consists of fictional/sample data created solely for demonstrating the functionality of the application. No personal information of real community members is included.
