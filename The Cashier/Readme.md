# The Cashier V 0.1
Aplikasi ini mencakup fungsi perhitungan harga barang atau jasa dengan banyaknya barang ataupun jasa

## Scope & Functionalities 
- User dapat memasukkan nama barang ataupun jasa
- User dapat menambahkan banyaknya barang yang ingin diinput
- User akan mendapatkan informasi secara otomatis mengenai total harga tanpa menyentuh tombol apapun

## How Does it Works

Diawali dari method `MainWindow` pada `class MainWindwo.xaml.cs` kita mendeklarasikan dengan
```csharp
 public partial class MainWindow : Window
    {
        private Calculator calculator;

        public MainWindow()
        {
            InitializeComponent();
            calculator = new Calculator();
            listBox.ItemsSource = calculator.getListItem();
        }
```

logika perhitungan dan penambahan barang disertai total harga pada kasir terdapat di `Calculator.cs`
``` csharp
 class Calculator
    {
        private List<Item> listItem;
        private double total = 0;

        public Calculator()
        {
            this.listItem = new List<Item>();
        }

        public void additem(Item item)
        {
            this.listItem.Add(item);
            this.total += item.getSubTotal();
        }

        public double getTotal()
        {
            return total;

        }

        public List<Item> getListItem()
        {
            return listItem;
        }
    }
```



