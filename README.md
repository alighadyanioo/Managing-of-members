# Managing(example)

       Scanner scanner = new Scanner(System.in);
        ArrayList<Visit> visits = new ArrayList<>();

        while (true) {
            printAction();
            int numberOfSwitch = scanner.nextInt();
            if (numberOfSwitch > 4) {
                System.out.println("Your Number is Out of The Range\nPlease Choose from 1 to 4...!!!");
            }
            switch (numberOfSwitch) {
                case 1 -> {
                    String name;
                    System.out.println("Please Enter the name:");
                    name = scanner.next();

                    boolean hasDuplication = false;
                    for (Visit visit : visits) {
                        if (visit.getName().equals(name)) {
                            hasDuplication = true;
                            break;
                        }
                    }

                    if (hasDuplication) {
                        System.out.println("Error>> " + name + " is a duplicate Name...!!!");
                    } else {
                        Visit visit = new Visit();
                        visit.setName(name);
                        visit.setDate(System.currentTimeMillis());

                        visits.add(visit);
                        System.out.println(name + " Added " + "in " + visit.getDate());
                    }
                }
                case 2 -> {
                    System.out.println("Please Enter the name:");
                    String removeName = scanner.next();

                    boolean hasVisit = false;
                    for (int i = visits.size() - 1; i >= 0; i--) {
                        if (removeName.equals(visits.get(i).getName())) {
                            System.out.println("Visit removed " + visits.get(i).getName());
                            visits.remove(i);
                            hasVisit = true;
                        }
                    }

                    if (!hasVisit) {
                        System.out.println("Visit Not Found...!!!");
                    }
                }
                case 3 -> {
                    System.out.println("Our List is:");
                    if (visits.size() == 0) {
                        System.out.println("Already Empty...!!!");
                    }
                    for (int i = visits.size() - 1; i >= 0; i--) {
                        System.out.println(visits.get(i) + " ");
                    }
                }
                case 4 -> {
                    if (visits.isEmpty()) {
                        System.out.println("You Don't Have Any Member to prove Any Time...!!!");
                    }

                    for (Visit visit : visits) {
                        System.out.println("The name is: " + visit.getName() + " and the date is: " + visit.getDate());
                    }
                }
            }
        }
    }

    public static void printAction() {
        System.out.println();
        System.out.println("1) Add Member");
        System.out.println("2) Delete Member");
        System.out.println("3) Show List");
        System.out.println("4) Show Time");
        System.out.print("Please Choose From 1 to 4 : ");
