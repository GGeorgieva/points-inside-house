import java.util.Scanner;
public class _9_PointsInsideHouse {

	public static void main(String[] args) {
		Scanner input=new Scanner(System.in);
		double nX=input.nextDouble();
		double nY=input.nextDouble();
		double aX=12.5;
		double aY=8.5;
		double bX=17.5;
		double bY=3.5;
		double cX=22.5;
		double cY=8.5;
		if ((isRightToLineA(aX,aY,bX,bY,nX,nY)
				&& isLefToLineB(bX,bY,cX,cY,nX,nY)
				&& isAboveLineC(nY))
				|| isInsideFirstRectangular(nX,nY)
				|| isInsideSecondRectangular(nX,nY)) {
			System.out.println("Inside");
		}
		else {
			System.out.println("Outside");
		}
		
	}
	public static boolean isRightToLineA(double aX, double aY, double bX, double bY, double nX,double nY){
	     return ((bX - aX)*(nY - aY) - (bY - aY)*(nX - aX)) >= 0;
	}
	public static boolean isLefToLineB(double bX, double bY, double cX, double cY, double nX,double nY){
	     return ((cX - bX)*(nY - bY) - (cY - bY)*(nX - bX)) >=0;
	}
	public static boolean isAboveLineC(double nY){
	     return nY <=8.5;
	}
	public static boolean isInsideFirstRectangular(double nX, double nY){
	     return (nX>=12.5&&nX<=17.5&&nY>=8.5&&nY<=13.5);
	}
	public static boolean isInsideSecondRectangular(double nX, double nY){
	     return (nX>=20&&nX<=22.5&&nY>=8.5&&nY<=13.5);
	}
}

