 private void button1_Click(object sender, EventArgs e)
        {
            string path = this.textBox1.Text;
            byte[] imgBytesIn = SaveImage(path);
            ShowImgByByte(imgBytesIn);
            //Parameters.Add("@Photo", SqlDbType.Binary).Value = imgBytesIn;
           
        }
        public byte[] SaveImage(String path)
        {            
            FileStream fs = new FileStream(path, FileMode.Open, FileAccess.Read);
            BinaryReader br = new BinaryReader(fs);
            byte[] imgBytesIn = br.ReadBytes((int)fs.Length);  
            return imgBytesIn;
        }
        public void ShowImgByByte(byte[] imgBytesIn)
        {
            MemoryStream ms = new MemoryStream(imgBytesIn);
            pictureBox1.Image = Image.FromStream(ms);
        }
==============================
