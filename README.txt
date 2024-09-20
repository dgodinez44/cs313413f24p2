For TestPerformance.java

private final int REPS = 100000;

SIZE = 10
Runtime: 25 ms

SIZE = 100
Runtime: 27 ms

SIZE = 1000
Runtime: 74 ms

SIZE = 10000
Runtime: 658 ms

SIZE = 100000
Runtime: 6 secs 406 ms

SIZE = 1000000
Runtime: 37 sec 875 ms

As size increases, runtime also increases.

For TestList.java

public void setUp() throws Exception {
    list = new LinkedList<Integer>();
    // TODO also try with a LinkedList - does it make any difference?
  }
 // ANSWER: This does not make any noticeable difference

 public void testRemoveObject() {
     list.add(3);
     list.add(77);
     list.add(4);
     list.add(77);
     list.add(5);
     list.add(77);
     list.add(6);
     list.remove(5); // what does this method do?
     // ANSWER: removes the element at index 5. In this case it removes 77.
     // TODO fix the expected values in the assertions below
     assertEquals(6, list.size());
     assertEquals(1, list.indexOf(77));
     assertEquals(3, list.lastIndexOf(77));
     assertEquals(4, list.get(2).intValue());
     assertEquals(77, list.get(3).intValue());
     list.remove(Integer.valueOf(5)); // what does this one do?
     // ANSWER: Get rids of last element or the element at index 5.
     // It removes 6.
     assertEquals(5, list.size());
     assertEquals(1, list.indexOf(77));
     assertEquals(3, list.lastIndexOf(77));
     assertEquals(4, list.get(2).intValue());
     assertEquals(77, list.get(3).intValue());
   }

   For TestIterator.java

   public void setUp() throws Exception {
       list = new LinkedList<Integer>();
       // TODO also try with a LinkedList - does it make any difference?
     }
     // ANSWER: Does not make a noticeable difference. Code still runs.

     public void testRemove() {
         list.add(33);
         list.add(77);
         list.add(44);
         list.add(77);
         list.add(55);
         list.add(77);
         list.add(66);
         final var i = list.iterator();
         while (i.hasNext()) {
           if (i.next() == 77) {
             i.remove(); // TODO what happens if you use list.remove(Integer.valueOf(77))?
             // ANSWER: Test does not pass if I use list.remove(Integer.valueOf(77)).
           }
         }
         // TODO using assertEquals and List.of, express which values are left in the list
         // See TestList.java for examples of how to use List.of; also see the Java List
         // interface for more information
         assertEquals(List.of(33, 44, 55, 66), list);
       }
