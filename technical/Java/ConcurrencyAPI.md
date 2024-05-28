
# ATOMIC INTEGER

private static AtomicInteger count = new AtomicInteger(0);

    public static void main(String[] args) {
        System.out.println("TYY");

        Thread thread1 = new Thread(() -> {
            for (int i = 0; i < 100000; i++) {
                count.incrementAndGet();
            }
        });
        Thread thread2 = new Thread(() -> {
            for (int i = 0; i < 100000; i++) {
                count.incrementAndGet();
            }
        });
        thread1.start();
        thread2.start();

        try {
            thread1.join();
        } catch (InterruptedException e) {
            System.out.println("thread1" + e.getMessage());
        }
        try {
            thread2.join();
        } catch (InterruptedException e) {
            System.out.println("thread2" + e.getMessage());
        }
        System.out.println(count);


    }