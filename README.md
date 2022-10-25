# Date-Program-in-C

#include <stdio.h>
#include <string.h>

struct Date {
	int day, month, year;  //these variables uses for getting input from user
};

int main(){
	struct Date d;
	
	//first s uses here for calculating Year days upto speicfied date then secondaly uses for storing weak days number
	int s= 0;       
	//these variable uses for setting month and weakday
	char month[15];
	char weakDay[15];
	
	printf("Enter Date : ");
	scanf("%d", &d.day);
	printf("Enter Month: ");
	scanf("%d",&d.month);
	printf("Enter Year: ");
	scanf("%d",&d.year);
	
	//Code for finding current day of specified date
	
	//for setting month value
	int mon[12] = {31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};
	
	//uses for checking leap year or not
	if((d.year % 4 == 0) || ((d.year % 4 == 0) && (d.year % 100 != 0))) {
		mon[1] = 29;
	}
	
	for (int i =0; i < d.month-1; i++){
		s = s + mon[i]; //uses for calculating days in year upto specified date
	}
	//This formula uses for getting weak day number
	s = s + (d.day + d.year + (d.year / 4) -2);
	s = s%7;
	
	//uses for getting desired day
	
	switch(s){
	case 0: 
		strcpy(weakDay, "sunday");
		break; 
	case 1: 
		strcpy(weakDay, "monday");
		break;
	case 2: 
		strcpy(weakDay, "tuesday");
		break;
	case 3: 
		strcpy(weakDay, "wednesday");
		break;
	case 4: 
		strcpy(weakDay, "thursday");
		break;
	case 5: 
		strcpy(weakDay, "friday");
		break;
	case 6: 
		strcpy(weakDay, "saturday");
		break;
	default: 
		printf("Not valid");
	}
	
	
	//Uses for getting desired month
	switch(d.month)
	{
	case 0: 
		strcpy(month, "January");
		break; 
	case 1: 
		strcpy(month, "february");
		break;
	case 2: 
		strcpy(month, "march");
		break;
	case 3: 
		strcpy(month, "april");
		break;
	case 4: 
		strcpy(month, "may");
		break;
	case 5: 
		strcpy(month, "june");
		break;
	case 6: 
		strcpy(month, "july");
		break;
	case 7: 
		strcpy(month, "august");
		break;
	case 8: 
		strcpy(month, "september");
		break;
	case 9: 
		strcpy(month, "october");
		break;
	case 10: 
		strcpy(month, "november");
		break;
	case 11: 
		strcpy(month, "december");
		break;		
	default: 
		strcpy(month, "Not valid");
	}
	//desired output form 
	printf("Day => %s , %d : %s , %d : %d", weakDay, d.month, month,d.year, d.year % 100);
	
	return 0;	
}
