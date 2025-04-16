Simply put, (IoC) is a process in which an object defines its dependencies without creating them. This object delegates the job of constructing such dependencies to an IoC container.

Assume we have a class declaration:
public class Company {
private Address address;

public Company(Address address) {
    this.address = address;
}

// getter, setter and other properties
}

This class needs a collaborator of type Address:
public class Address {
private String street;
private int number;

public Address(String street, int number) {
    this.street = street;
    this.number = number;
}

// getters and setters
}

Normally, we create objects with their classes’ constructors:
Address address = new Address("High Street", 1000);
Company company = new Company(address);

Instead of constructing dependencies in this way , an object can retrieve its dependencies from an IoC container. All we need to do is to provide the container with appropriate configuration metadata.

Here’s a configuration class supplying bean metadata to an IoC container:
@Configuration
@ComponentScan(basePackageClasses = Company.class)
public class Config {
@Bean
public Address getAddress() {
return new Address("High Street", 1000);
}
}

The configuration class produces a bean of type Address.