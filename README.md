using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace WindowsFormsApp1
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void textBox1_TextChanged(object sender, EventArgs e)
        {
            List<int> list = textBox1.Text
                 .Split(new char[] { ' ', ',', ';', '\n', '\r' },
                 StringSplitOptions.RemoveEmptyEntries).Select(s => int.Parse(s)).ToList();

            chart1.Series[0].Points.Clear();
            chart1.Series[0].Points.DataBindY(list);
        }
    }
}
