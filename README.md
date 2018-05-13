import java.util.function.BiConsumer;

public class ExceptionHandlingJava8 {
    public static void main(String[] args){
        int [] someNumbers = {2,2,2,4,6};
        int key=2;

        process(someNumbers, key, wrapperLambda((a,b) -> System.out.println(a/b)));
    }
    private static void process(int [] someNumbers, int key, BiConsumer<Integer, Integer> consumer){
        for (int i : someNumbers){
                consumer.accept(i, key);
        }
    }

    private static BiConsumer<Integer, Integer> wrapperLambda(BiConsumer<Integer, Integer> consumer){
        return (a,b) ->{
            try {
                consumer.accept(a, b);
            }catch(ArithmeticException e){
                System.out.println("An arithmetic exception occured");
            }
        };

    }

}

