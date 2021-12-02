# ProjektOOP
 class FigureCircle : IFigures
    {
        public string FigureName { get; private set; }
        private int Perimeter;
        private double Radius;
        private Coordinate Positions;
        


        public FigureCircle(float posX, float posY, int _perimeter)
        {
            FigureName = "CIRCLE";   
            Perimeter = _perimeter;
            Radius = PerToRad();
            Positions = new Coordinate(posX, posY);
        }

        private double PerToRad()
        {
            return Perimeter / (2 * Math.PI);
        }

        public double FigureArea()
        {
            return Math.Pow(Radius, 2) * Math.PI;
        }

        public bool PointInFigure()
        {
            //om värdet på x^2 + y^2 är mindre eller lika med radien upphöjt till två så ligger punkten i figuren.
            double RadiusSqrt = (Math.Pow(Positions.PosX, 2) + Math.Pow(Positions.PosY, 2));
            
            if (RadiusSqrt > Math.Pow(PerToRad(), 2))
            {
                return false;
            }
            else if (RadiusSqrt <= Math.Pow(PerToRad(), 2))
            {
                return true;
            }
            
        }

    }
