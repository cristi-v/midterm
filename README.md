# midterm
midterm project 
import processing.sound.*;

SoundFile song;

void setup() {
  size(400,400);
  background(255);
  song = new SoundFile(this,"Slippage-2.wav");
  song.loop();
}
void draw(){ 
  float volume = map(mouseX,0,width,0,1);
  song.amp(volume);
  
  float speed = map(mouseY,0,height,0,2);
  song.rate(speed);
  
  background(255);
  int i =0;
  for (i=0; i < 400; i += random(5)) {
    noFill();
    stroke(random(255),random(255),random(255));
    bezier(width,height/2,mouseX,mouseY,mouseX,mouseY,0,i);
  }

}
