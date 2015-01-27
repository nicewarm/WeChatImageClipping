# WeChatImageClipping

现在IM  都在仿微信，我也是遇到这种需求之后，写的这个图片剪裁，效果如下：<br/>

 ![image] (https://github.com/nicewarm/WeChatImageClipping/blob/master/image/clipping.png)
 
 主要代码如下：<br/>
 
    Bitmap roundConcerImage = Bitmap.createBitmap(500,500, Config.ARGB_8888);
    Canvas canvas = new Canvas(roundConcerImage);
    Paint paint = new Paint();
    Rect rect = new Rect(0,0,500,500);
    Rect rectF = new Rect(0, 0, bitmap_in.getWidth(), bitmap_in.getHeight());
    paint.setAntiAlias(true);
    NinePatch patch = new NinePatch(bitmap_bg, bitmap_bg.getNinePatchChunk(), null);
    patch.draw(canvas, rect);
    paint.setXfermode(new PorterDuffXfermode(Mode.SRC_IN));
    canvas.drawBitmap(bitmap_in, rectF, rect, paint);
		
