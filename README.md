public class JvmComprehension {

    public static void main(String[] args) { // В стек помещается сигнатура метода main прежде всего
        int i = 1;                      // 1 Во фрейме main в стеке создается примитив int i = 1
        Object o = new Object();        // 2 Переменная o создается в стеке и хранит в себе ссылку на объект
                                        // Object, попадающий в heap (куча)
        Integer ii = 2;                 // 3 Переменная ii создается в стеке и хранит в себе ссылку на объект
                                        // Integer, принимающий значение 2
        printAll(o, i, ii);             // 4 В стек помещается сигнатура метода printAll. В его фрейме
                                        // создается примитив i и ссылки на объекты o и ii, сами объекты Object и
                                        // Integer попадают в heap
        System.out.println("finished"); // 7 создается новый фрейм println в стеке, принимающий ссылку на
                                        // объект типа String в куче, со значением "finished"
    }

    private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;                   // 5 в стеке создается переменная uselessVar,
                                                    // ссылающаяся на объект Integer в куче, принимающий
                                                    // значение 700, созданная во фрейме printAll
        System.out.println(o.toString() + i + ii);  // 6 в стеке создается новый фрейм println и примитив i,
                                                    // принимающий ссылки на объекты o и ii, находящиеся в куче,
                                                    // а также значение примитива i
    }
}