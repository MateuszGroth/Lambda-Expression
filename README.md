# Lambda-Expression
//Java 8 practise

import java.util.Arrays;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
import java.util.function.Predicate;



public class ExerciseSolutionJava8 {

    public static void main(String[] args) {
        List<Person> people = Arrays.asList(
                new Person("Charles", "Dickens", 60),
                new Person("Lewis", "Caroll", 42),
                new Person("Thomas", "Calyle", 51),
                new Person("Charlotte", "Bronte", 45),
                new Person("Matthew", "Arnold", 39)
        );
        //Sorting
        Collections.sort(people, (p1, p2) -> p1.getLastName().compareTo(p2.getLastName()));
        //Step 1 - sorting by last name
        printConditionally(people, p -> true);
        //Step 2 - Create a method that prints all elements in the list
        //Step 3 - create a method that prints all peaople that have last name beggining with C
        System.out.println("Starts with C");
        printConditionally(people, (p) -> p.getLastName().startsWith("C"));
    }
    private static void printAll (List <Person> people){
        for (Person p : people) {
            System.out.println(p);
        }
    }
    private static void printConditionally(List<Person> people, Predicate<Person> predicate){
        for (Person p : people){
            if(predicate.test(p)) System.out.println(p);
   }
    }
}

