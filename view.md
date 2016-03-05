import processing.pdf.*;

PImage colorImg;

void setup()
{
  colorImg = loadImage("face_parts.png");

  size(600, 700);
//  String s = "save_" + nf(day(), 2) + nf(hour(), 2) + nf(minute(), 2) + nf(second(), 2) + ".pdf";
//  beginRecord(PDF, s);
  background(255);

  //noLoop();
}

void draw() {

  //  image(colorImg, 0, 0);
  stroke(242, 47, 160);

  for (float y = 100; y <= height; y *= 1.01)
  {
    for (float x = 10; x <= width-10; x += 8) 
    {
      color c = colorImg.get(int(x), int(y));
      int br = int(255 - brightness(c)); 
      float size = 10*br/255;
      strokeWeight(size);
      line (x, y-5, x, y);
    }
  }
//  endRecord(); //insert the line here
}
