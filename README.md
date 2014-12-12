Converting-Number-to-Words-and-Romans
=====================================
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace Project
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            string[] Ones = { "One", "Two", "Three", "Four", "Five", "Six", "Seven", "Eight", "Nine", "Ten", "Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen", "Sixteen", "Seventeen", "Eighteen", "Ninteen" };
            string[] Tens = { "Ten", "Twenty", "Thirty", "Fourty", "Fift", "Sixty", "Seventy", "Eighty", "Ninty" };

            int no = int.Parse(txtNumber.Text);
            string strWords = "";

            if (no > 999 && no < 10000)
            {
                int i = no / 1000;
                strWords = strWords + Ones[i - 1] + " Thousand ";
                no = no % 1000;
            }


            if (no > 99 && no < 1000)
            {
                int i = no / 100;
                strWords = strWords + Ones[i - 1] + " Hundred ";
                no = no % 100;
            }

            if (no > 19 && no < 100)
            {
                int i = no / 10;
                strWords = strWords + Tens[i - 1] + " ";
                no = no % 10;
            }

            if (no > 0 && no < 20)
            {
                strWords = strWords + Ones[no - 1];
            }

            lblWords.Text = strWords;
        }
    }
}


