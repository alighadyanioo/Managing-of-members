# multiply
multiply two number with out * operator
        Scanner scanner = new Scanner(System.in);
        System.out.println("please enter the first number:");
        int firstnumber = scanner.nextInt();
        System.out.println("please enter the second number:");
        int secondnumber = scanner.nextInt();
        int sum = 0;

        for(int i = 1; i <= firstnumber; ++i) {
            sum += secondnumber;
        }

        System.out.println("Result:" + sum);
