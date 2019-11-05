# unit-11
11-1
public class SimpleGeometricObject {
	private String color = "white";
	private boolean filled;
	private java.util.Date dataCreated;
	
	public SimpleGeometricObject() {
		dataCreated = new java.util.Date();
	}
	
	public SimpleGeometricObject(String color, boolean filled) {
		dataCreated = new java.util.Date();
		this.color = color;
		this.filled = filled;
	}
	
	public String getColor() {
		return color;
	}
	
	public void setColor(String color) {
		this.color = color;
	}
	
	public boolean isFilled() {
		return filled;
	}
	
	public void setFilled(boolean filled) {
		this.filled = filled;
	}
	
	public java.util.Date getDateCreated(){
		return dataCreated;
	}
	
	public String toString() {
		return "created on" + dataCreated + "\ncolor: " + color +
				" and filled: " + filled;
	}
}

11-2
package simplegeometricobject;

public class circleformsimplegeometricobject 
     extends SimpleGeometrecObject
  private double radius;

  public circleformsimplegeometricobject(){
  }
  
  public circleformsimplegeometricobject(double radius){
	  this.radius = radius;
  }
  
  public circleformsimplegeometricobject(double radius,
		  String color, boolean filled){
	  this.radius = radius;
	  setColor(color);
	  setFilled(filled);
  }
  
  public double getRadius(){
	  return radius;
  }
  
  public void setRadius(double radius){
	  this.radius = radius;
  }
  
  public double getArea(){
	  return radius * radius *Math.PI;
  }
  
  public double getDiameter(){
	  return 2 * radius;
  }
  
  public double getPerimeter(){
	  return 2 * radius *Math.PI;
  }
  
  public void printCircle(){
	  System.out.println("the circle is created " + getDateCreates() + " and the radius is "
			  + radius);
  }
}

11-3
public class RectangleFromSimpleGeotricObject 
     extends SimpleGeometricObject{
	private double width;
	private double height;
	
	public RectangleFromSimpleGeotricObject() {	
	}
	
	public RectangleFromSimpleGeotricObject(double width,double height) {
		this.width = width;
		this.height = height;
	}
	
	public RectangleFromSimpleGeotricObject(
			double width,double height,String color,boolean filled) {
		this.width = width;
		this.height = height;
	}
	
	public double getWidth() {
		return width;
	}
	
	public void setWidth(double width) {
		this.width = width;
	}
	
	public double getHeight() {
		return height;
	}
	
	public void setHeight(double height) {
		this.height = height;
	}
	
	public double getArea() {
		return width *height;
	}
	
	public double getPerimeter() {
		return 2*(width + height);
	}
}

11-4
public class TestCircleRectangle {

	public static void main(String[] args) {
		CircleFromSimpleGeometricObject circle =
				new CircleFromSimpleGeometricObject(1);
		System.out.println("A circle " + circle.toString());
		System.out.println("The color is " + circle.getcolor());
		System.out.println("The radius is " + circle.getRadius());
		System.out.println("The area is " + circle.getArea());
		System.out.println("The diameter is " + circle.getDiameter());
		
		RectangleFromSimpleGeometricObject rectangle =
				new RectangleFromSimpleGeometricObject(2,4);
		System.out.println("\nA rectangle " + rectangle.toString());
		System.out.println("The area is" + rectangle.getArea());
		System.out.println("The perimeter is " + rectangle.getPerimeter());
	}
}

11-5
public class PolymorphismDemo {
	public static void main(String[] args) {
		displayObject(new CircleFromSimpleGeometricObject(1,"red",false));
		displayObject(new RectangleFromSimpleGeometricObject(1,1,"black",true));
	}
	
	public static void displayObject(SimpleGeometricObject object) {
		System.out.println("Greated on " + object.getDateCreated() + ". Color is " +
	 object.getColor());
	}
}

11-6
public class DynamicBindingDemo {
	public static void main(String[] args) {
		m(new GraduateStudent());
		m(new Student());
		m(new Person());
		m(new Object());
	}
	
	public static void m(Object x) {
		System.out.println(x.toString());
	}
}
class GraduateStudent extends Student{
}

class Student extends Person{
	@Override
	public String toString() {
		return "Student" ;
	}
}
class Person extends Object{
	@Override
	public String toString() {
		return "Person";
	}
}

11-7
public class CastingDemo {

	public static void main(String[] args) {
		Object object1 = new CircleFormSimpleGeometricObject(1);
		Object object2 = new RectangleFromSimpleGeometricObject(1,1);
		
		displayObject(object1);
		displayObject(object2);
	}
	
	public static void displayObject(Object object) {
		if(object instanceof CircleFromSimpleGeometricObject) {
			System.out.println("the circle area is " + ((CircleFromSimpleGeometricObject)object).getArea());
			System.out.println("the circle diameter is " + ((CircleFromSimpleGeometricObject)object).getDiameter());
		}
		else if (object instancof  RectangleFromSimpleGeometricObject) {
			System.out.println("The rectangle area is " + (( RectangleFromSimpleGeometricObject)object).getArea());
		}
	}
}
