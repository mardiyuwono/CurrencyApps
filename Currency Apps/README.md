# Currency Apps
(Introduction)  
Aplikasi ini merupakan contoh sederhana membangun aplikasi dekstop windows.

## Scope of functionalities
User dapat mengkonversi nilai dollar menjadi rupiah
User mendapat keterangan "invalid" apabila memasukkan huruf

## How does it works?
Diawali dari Method  `MainWindow`  pada class  `MainWindow.xaml.cs`  kita mendeklarasikan
```C#
public MainWindow()
        {
            InitializeComponent();
            currency = new CurrencyController();
        }
```
Logika perhitungan terdapat pada class  `CurrencyController.cs`  sbb :
```C#
public string UsdToIdr(string nominal)
        {
            var nominalDouble = Convert.ToDouble(nominal);
            var result = nominalDouble * 15000;
            return Convert.ToString(result);
        }

        public Boolean IsAllowed(string nominal)
        {
            Regex regex = new Regex("[^0-9.-]+");
            return !regex.IsMatch(nominal);
        }
  ```