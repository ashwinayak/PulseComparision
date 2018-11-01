# PulseComparision
Remote Pulse Comparison Code


package pulse_compare1;

/** 
 * 
 * @author Ashwin Nayak  
 */
public class Pulse_compare {

 String[] new_arr1;
    String[] new_arr2;
    String[] new_arr3;
    String[] new_check;
    String[] temp;
    public Pulse_compare1(String[] new_arr1,String[] new_arr2,String[] new_arr3,String[] new_check,String[] temp)
    {
        this.new_arr1=new_arr1;
        this.new_arr2=new_arr2;
        this.new_arr3=new_arr3; 
        this.new_check=new_check;
        this.temp=temp;   
    }
    public void pulsedifference(String arr1[],String arr2[],float tolerance)//,String[] new_arr1,String[] new_arr2,String[] new_arr3,String[] new_check)
    {
        int j=0,count=0; 
        int x=0,y=0;
      
        //System.out.println("Position    Pulse X   PulseY    Difference %    Tolerance given: "+tolerance*100+"%");
        int lenght=(arr1.length>arr2.length)?arr1.length:arr2.length;
         String yesno[]=new String[lenght];
          float dp[] = new float[lenght];
        for(int i=0;i<lenght;i++)
        {
            if(arr1.length>i && arr2.length>i)
            {
         x=Integer.parseInt(arr1[i]);
         y=Integer.parseInt(arr2[j]);
        if((Math.abs(x-y))<=(tolerance*x))
        {
        yesno[i]="YES";
        new_check[i]=yesno[i];
        count++;
        }
        else
        {
            yesno[i]="!-----NO------!";
            new_check[i]=yesno[i];
        }
       
        dp[i]=(float)((Math.abs(x-y))/(float)x);
        new_arr1[i]=arr1[i];
        new_arr2[j]=arr2[j];
        new_arr3[i]=Integer.toString(Math.round(dp[i]*100));
               
                j++;
        }
            else if(arr1.length>i && arr2.length-1<i){
                yesno[i]="NO";
                new_check[i]=yesno[i];
                new_arr1[i]=arr1[i];
                new_arr2[i]="NULL";
                new_arr3[i]="NULL";
             
            }
            
            else if(arr1.length-1<i && arr2.length>i)
            {
                yesno[i]="NO";
                new_arr1[i]="NULL";
                new_arr2[i]=arr2[j];
                new_arr3[i]="NULL";
                new_check[i]=yesno[i];
              
            }
        }
        if(count==arr1.length)
            temp[0]="RESULT MATCHED";
           
        else
            temp[0]="RESULTS UNMATCHED";
           
    }
}
