# boom3d_trialreset
Pretty easy trial reset for Boom3D

Just delete the key:

HKEY_CURRENT_USER\Software\{8A02D897-5A3E-4139-91FD-F8377DD6132C}

------------------------------------------------------------------

You can decrypt the data with:

        private static string FromHexString(object hexStr)
        {
            string text = hexStr.ToString();
            byte[] array = new byte[text.Length / 2];
            for (int i = 0; i < array.Length; i++)
            {
                array[i] = System.Convert.ToByte(text.Substring(i * 2, 2), 16);
            }
            return System.Text.Encoding.Unicode.GetString(array);
        }
        
To convert it back use:

        private static string ToHexString(object str)
        {
            System.Text.StringBuilder stringBuilder = new System.Text.StringBuilder();
            foreach (byte b in System.Text.Encoding.Unicode.GetBytes(str.ToString()))
            {
                stringBuilder.Append(b.ToString("X2"));
            }
            return stringBuilder.ToString();
        }
        
