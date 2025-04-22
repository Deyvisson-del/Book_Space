# Book_Space

class


public class Main {
    public static void main(String[] args) {
        printEmployee(new Maneger());
        printEmployee(new Salesman());
    }

    public static void printEmployee(Employee employee) {

        System.out.printf("========%s=======\n", employee.getClass().getCanonicalName());
        switch (employee){
            case Maneger maneger ->{
                maneger.setCode("123");
                maneger.setName("João");
                maneger.setSalary(5000);
                maneger.setLogin("joao");
                maneger.setPassword("123456");
                maneger.setCommission(1200);


                System.out.println(maneger.getCode());
                System.out.println(maneger.getSalary());
                System.out.println(maneger.getName());
                System.out.println(maneger.getLogin());
                System.out.println(maneger.getPassword());
                System.out.println(maneger.getCommission());
            }
            case Salesman salesman -> {
                salesman.setCode("456");
                salesman.setName("Lucas");
                salesman.setSalary(2800);
                salesman.setPercentPerSold(10);


                System.out.println(salesman.getCode());
                System.out.println(salesman.getSalary());
                System.out.println(salesman.getName());
                System.out.println(salesman.getPercentPerSold());
            }
            default -> throw new IllegalStateException("Unexpected value: " + employee);
        }
        System.out.printf("========Final =======\n");
    }
}



classe maneger 

public non-sealed class Maneger extends Employee  {
    private String login;
    private String password;
    private double commission;

    public String getLogin() {
        return login;
    }

    public void setLogin(String login) {
        this.login = login;
    }

    public double getCommission() {
        return commission;
    }

    public void setCommission(double commission) {
        this.commission = commission;
    }

    public String getPassword() {
        return password;
    }

    public void setPassword(String password) {
        this.password = password;
    }
}

classe salesman

public non-sealed class Salesman extends Employee {
    private double percentPerSold;

    public double getPercentPerSold() {
        return percentPerSold;
    }

    public void setPercentPerSold(double percentPerSold) {
        this.percentPerSold = percentPerSold;
    }
}

classe Employee

public sealed class Employee permits Maneger, Salesman {
    private String code;
    private String name;
    private String address;
    private int age;
    private double salary;

    public double getSalary() {
        return salary;
    }

    public void setSalary(double salary) {
        this.salary = salary;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public String getAddress() {
        return address;
    }

    public void setAddress(String address) {
        this.address = address;
    }

    public String getCode() {
        return code;
    }

    public void setCode(String code) {
        this.code = code;
    }
}
