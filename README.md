# csharp
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace harfüretme
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }
        int[] kutu2 = new int[5];
        private void button1_Click(object sender, EventArgs e)
        {
                Random rastgele = new Random();
                char harf;
                string kelime = "";
                int sayac = 0;
                for (int i = 0; i < 5; i++)
                {
                    int rdn = rastgele.Next(2, 16);
                    for (int a = 1; a < rdn; a++)
                    {
                        int kod = rastgele.Next(65, 91);
                        harf = Convert.ToChar(kod);
                        kelime += Convert.ToString(harf); 
                        sayac = a;
                    }
                    listBox1.Items.Add(kelime);
                    kelime = "";
                    listBox2.Items.Add(sayac + " harf");
                    kutu2[i] = sayac;
                }
               
        }
        private void button2_Click(object sender, EventArgs e)
        {
                for (int i = 0; i < 5; i++)
                {
                    listBox3.Items.Add(Convert.ToString(kutu2[i]) + " " + Convert.ToString(listBox1.Items[i]));
                }

            
        }
    }
}
