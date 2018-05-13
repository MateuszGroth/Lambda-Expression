import java.util.function.BiConsumer;

public class ExceptionHandlingJava8 {
    public static void main(String[] args){
        int [] someNumbers = {2,2,0,4,6};
        int key=2;

        process(someNumbers, key, (a,b) -> System.out.println(b/a));
    }
    private static void process(int [] someNumbers, int key, BiConsumer<Integer, Integer> consumer){
        for (int i : someNumbers){
            try {
                consumer.accept(i, key);
            }catch(Exception e){
                System.out.println("Error, dont divide by 0");
            }
        }
    }
}


