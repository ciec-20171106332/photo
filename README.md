 private void button1_Click(object sender, EventArgs e)
        {
            string path = this.textBox1.Text;
            byte[] imgBytesIn = SaveImage(path);
            ShowImgByByte(imgBytesIn);
            //Parameters.Add("@Photo", SqlDbType.Binary).Value = imgBytesIn;
           
        }
        //将图片以二进制流
        public byte[] SaveImage(String path)
        {            
            FileStream fs = new FileStream(path, FileMode.Open, FileAccess.Read); //将图片以文件流的形式进行保存
            BinaryReader br = new BinaryReader(fs);
            byte[] imgBytesIn = br.ReadBytes((int)fs.Length);  
            return imgBytesIn;
        }
      =====
