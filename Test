using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
using System.IO.Ports;
using System.Diagnostics;
namespace TEST_PLC_VsCode_V3
{
    public partial class Modbus_page : Form
    {
        SerialPort _serialPort = new SerialPort("COM4", 9600, Parity.None, 8, StopBits.One);
        // Set the read/write timeouts  
        public Modbus_page()
        {
            InitializeComponent();
           
        }
        public  int CRC16(int[] buf, int len)
        {
            int crc = 0xFFFF;
            for (int pos = 0; pos < len; pos++)
            {
                crc ^= (int)buf[pos];        // XOR byte into least sig. byte of crc
                for (int i = 8; i != 0; i--)
                {    // Loop over each bit
                    if ((crc & 0x0001) != 0)
                    {      // If the LSB is set
                        crc >>= 1;                    // Shift right and XOR 0xA001
                        crc ^= 0xA001;
                    }
                    else
                    {                        // Else LSB is not set
                        crc >>= 1;                    // Just shift right
                    }
                }
            }

            return crc;
        }
        private void RelayOnBtn1_Click(object sender, EventArgs e)
        {
            // Makes sure serial port is open before trying to write  
            try
            {
                if (!(_serialPort.IsOpen))
                {
                    _serialPort.Open();
                }
                else
                {
                    //string message = "01 05 00 00 FF 00 8C 3A";
                    byte[] bytestosend = { 0x01, 0x05,0x00,0x00,0xFF,0x00,0x8C,0x3A };
                    _serialPort.Write(bytestosend, 0, bytestosend.Length);
                    
                    //message = _serialPort.ReadLine();
                    //Debug.WriteLine(message);
                    //  _serialPort.Write("FF 03 03 E8 00 01 11 A4");
                }
            }
            catch (Exception ex)
            {
                MessageBox.Show("Error opening/writing to serial port :: " + ex.Message, "Error!");
            }
        }


        private void button1_Click(object sender, EventArgs e)
        {
            // Makes sure serial port is open before trying to write  
            try
            {
                if (!(_serialPort.IsOpen))
                {
                    _serialPort.Open();
                }
                else
                {
                    byte[] bytestosend = { 0x01, 0x05, 0x00, 0x00, 0x00, 0x00, 0xCD, 0xCA };
                    _serialPort.Write(bytestosend, 0, bytestosend.Length);
                }
            }
            catch (Exception ex)
            {
                MessageBox.Show("Error opening/writing to serial port :: " + ex.Message, "Error!");
            }
        }

        private void RelayOnBtn2_Click(object sender, EventArgs e)
        {
            try
            {
                if (!(_serialPort.IsOpen))
                {
                    _serialPort.Open();
                }
                else
                {
                    byte[] bytestosend = { 0x01, 0x05, 0x00, 0x01, 0xFF, 0x00, 0xDD, 0xFA };
                    _serialPort.Write(bytestosend, 0, bytestosend.Length);
                }
            }
            catch (Exception ex)
            {
                MessageBox.Show("Error opening/writing to serial port :: " + ex.Message, "Error!");
            }
        }

        private void RelayOffBtn2_Click(object sender, EventArgs e)
        {
            try
            {
                if (!(_serialPort.IsOpen))
                {
                    _serialPort.Open();
                }
                else
                {
                    byte[] bytestosend = { 0x01, 0x05, 0x00, 0x01, 0x00, 0x00, 0x9C, 0x0A };
                    _serialPort.Write(bytestosend, 0, bytestosend.Length);
                }
            }
            catch (Exception ex)
            {
                MessageBox.Show("Error opening/writing to serial port :: " + ex.Message, "Error!");
            }
        }

        private void RelayOnBtn3_Click(object sender, EventArgs e)
        {
            try
            {
                if (!(_serialPort.IsOpen))
                {
                    _serialPort.Open();
                }
                else
                {
                    byte[] bytestosend = { 0x01, 0x05, 0x00, 0x02, 0xFF, 0x00, 0x2D, 0xFA };
                    _serialPort.Write(bytestosend, 0, bytestosend.Length);
                }
            }
            catch (Exception ex)
            {
                MessageBox.Show("Error opening/writing to serial port :: " + ex.Message, "Error!");
            }
        }

        private void RelayOffBtn3_Click(object sender, EventArgs e)
        {
            try
            {
                if (!(_serialPort.IsOpen))
                {
                    _serialPort.Open();
                }
                else
                {
                    byte[] bytestosend = { 0x01, 0x05, 0x00, 0x02, 0x00, 0x00, 0x6C, 0x0A };
                    _serialPort.Write(bytestosend, 0, bytestosend.Length);
                }
            }
            catch (Exception ex)
            {
                MessageBox.Show("Error opening/writing to serial port :: " + ex.Message, "Error!");
            }
        }

        private void RelayOnBtn4_Click(object sender, EventArgs e)
        {
            try
            {
                if (!(_serialPort.IsOpen))
                {
                    _serialPort.Open();
                }
                else
                {
                    byte[] bytestosend = { 0x01, 0x05, 0x00, 0x03, 0xFF, 0x00, 0x7C, 0x3A };
                    _serialPort.Write(bytestosend, 0, bytestosend.Length);
                }
            }
            catch (Exception ex)
            {
                MessageBox.Show("Error opening/writing to serial port :: " + ex.Message, "Error!");
            }
        }

        private void RelayOffBtn4_Click(object sender, EventArgs e)
        {
            try
            {
                if (!(_serialPort.IsOpen))
                {
                    _serialPort.Open();
                }
                else
                {
                    byte[] bytestosend = { 0x01, 0x05, 0x00, 0x03, 0x00, 0x00, 0x3D, 0xCA };
                    _serialPort.Write(bytestosend, 0, bytestosend.Length);
                }
            }
            catch (Exception ex)
            {
                MessageBox.Show("Error opening/writing to serial port :: " + ex.Message, "Error!");
            }
        }
    }
}
