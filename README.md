# Bresinaim-Circule-
c# implement algorithm
{{{{{{
{{{{{
int a;



        //ציור מעגל ברזנהיים 
        private void Bres_Circule(Point N, Point center)
        {

            int x = 0;
            int y = (int)Math.Sqrt((Math.Pow(center.X - N.X, 2) + Math.Pow(center.Y - N.Y, 2)));
            int p = 3 - 2 * y;
            while(x < y)
            {
                plot(x, y, center);
                if (p < 0) p = p + 4 * x + 6;
                else
                {
                    plot(x+1, y, center);//זה עניין ה closed corners 
                    p = p + 4 * (x - y) + 10;
                    y = y - 1;
                }
                x += 1;
            }
            if (x == y)
            {
                plot(x, y, center);
            }



        }
        //ציור הנקודות באופן סימטרי על המעגל ככמות גודל הרדיוס ועם התיקון פינות כפול 2
        private void plot( int x, int y, Point center)
        {
            PixelSet(new Point(center.X + x, center.Y + y));
            PixelSet(new Point(center.X - x, center.Y + y));
            PixelSet(new Point(center.X + x, center.Y - y));
            PixelSet(new Point(center.X - x, center.Y - y));

            PixelSet(new Point(center.X + y, center.Y + x));
            PixelSet(new Point(center.X - y, center.Y + x));
            PixelSet(new Point(center.X + y, center.Y - x));
            PixelSet(new Point(center.X - y, center.Y - x));


        }

