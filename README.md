/*
# Introduction_to_Java_Programming-_Comprehensive_Version_by_Y_Daniel
حل بعض الاسأله والمسائل في هذا الكتاب


*10.11 (Geometry: The Circle2D class) Define the Circle2D class that contains:
■ Two double data fields named x and y that specify the center of the circle with
get methods.
■ A data field radius with a get method.
■ A no-arg constructor that creates a default circle with (0, 0) for (x, y) and 1 for
radius.
■ A constructor that creates a circle with the specified x, y, and radius.
■ A method getArea() that returns the area of the circle.
■ A method getPerimeter() that returns the perimeter of the circle.
■ A method contains(double x, double y) that returns true if the specified
point (x, y) is inside this circle (see Figure 10.15a).
■ A method contains(Circle2D circle) that returns true if the specified
circle is inside this circle (see Figure 10.15b).
■ A method overlaps(Circle2D circle) that returns true if the specified
circle overlaps with this circle (see Figure 10.15c).
Draw the UML diagram for the class and then implement the class. Write a test
program that creates a Circle2D object c1 (new Circle2D(2, 2, 5.5)), displays
its area and perimeter, and displays the result of c1.contains(3, 3),
c1.contains(new Circle2D(4, 5, 10.5)), and c1.overlaps(new
Circle2D(3, 5, 2.3)).

*/

public class Example_10 {

  
    public static void main(String[] args) {
        Circle2D c1 = new Circle2D(2, 2, 5.5) ;
        
        System.out.println("the Area of Circle2D = " + c1.getArea());
        System.out.println("the Perimeter of Circle2D = " + c1.getPerimeter());
        System.out.println("IS the specified point (x, y) is inside this circle? : "+
                c1.contains(3, 3));
        System.out.println("IS the specified circle is inside this circle? : "+
                c1.contains(new Circle2D(4, 5, 10.5)));
        System.out.println(" IS the specified circle overlaps with this circle? : "+
                c1.overlaps(new Circle2D(3, 5, 2.3)) );
    }
    
}

class Circle2D
{
    private double x , y ;
    private double radius ;
    
    public Circle2D()
    {
        this.x = 0 ;
        this.y = 0 ;
        this.radius = 1 ;
    }

    public Circle2D(double x, double y, double radius) {
        this.x = x;
        this.y = y;
        this.radius = radius;
    }

    public double getX() {
        return x;
    }

    public double getY() {
        return y;
    }

    public double getRadius() {
        return radius;
    }
    
    public double getArea()
    {
        return Math.PI*radius*radius ;
    }
    
    public double getPerimeter()
    {
        return 2*Math.PI*radius ;
    }
    
    public boolean contains(double new_x, double new_y)
    {
        if(new_x >= (x-radius) && new_x <= (x+radius) && new_y >= (y-radius) && new_y <=(y+radius))
            return true ;
        else
            return false ;
    }
    
    public boolean contains(Circle2D circle)
    {
        if((circle.x-circle.radius) >= (x-radius) && (circle.x+circle.radius) <= (x+radius) &&
           (circle.y-circle.radius) >= (y-radius) && (circle.y+circle.radius) <= (y+radius)  )
            return true ;
        else
            return false ;
    }
    
    public boolean overlaps(Circle2D circle)
    {
        if( ((x-radius) < (circle.x-circle.radius) || (x+radius) > (circle.x+circle.radius)) &&
            ((y-radius) < (circle.y-circle.radius) || (y+radius) > (circle.y+circle.radius))  )
            return true ;
        else
            return false ;
    }
}
