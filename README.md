## Home_Assistant : Activity 2
## Platform : Android.

Student Name  | Student ID
------------- | -------------
Amrik Singh Sidhu  | C0742318

### Particle Code:

#include <InternetButton.h>

InternetButton button = InternetButton();
void setup() {
    button.begin();
    
    Particle.function("command",command);
   
}

void loop() {   }
    
  int command(String cmd)
{
    if( cmd == "loop")
    {
    for(int i=1;i<=11;i++)
    {
    button.ledOn(i,255,255,255);
    delay(2000);
    }
    delay(5000);
    button.allLedsOff();
    }
    
    if(cmd == "music")
    {
         button.allLedsOn(255,17,180);
    button.playSong("D6,8,B9,8,5,G11,8,6,D6,8");
    delay(1000);
    button.allLedsOff();
    }
    
     if(cmd == "rainbow")
    {
        button.rainbow(50);
    
    delay(5000);
    button.allLedsOff();
    }
    
       if(cmd == "goodbye")
    {
        button.allLedsOff();
    }
    
}

### Youtube Reference :
#### https://www.youtube.com/watch?v=nzkrRQgCEmE

