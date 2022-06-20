# demo

Форма WPF (.NET Framwork ) 
C# XAML Windows Рабочий стол



Добавиьт элемент -> Model ADO.NET EDM 
Для работы с БД в приложении ищем файл Model1.edmx -> Model1.Context.cs
        private static SchoolEntities _context; - нужно прописать
        public SchoolEntities()
            : base("name=SchoolEntities")
        {
        }
        public static SchoolEntities GetContext() - нужно прописать
        {
            if (_context == null)
                _context = new SchoolEntities();
            return _context;
        }
        
  Вывод данных в <DataGrid>
   <DataGrid Width="auto" Height="300" AutoGenerateColumns="False" IsReadOnly="True" x:Name="DGStaff">
        <DataGrid>
            <DataGrid.Columns>
                <DataGridTextColumn Header="ID" Binding="{Binding ID}"></DataGridTextColumn>
                <DataGridTextColumn Header="FirstName" Binding="{Binding FirstName}"></DataGridTextColumn>
                </DataGrid.Columns>
        </DataGrid>
     
     Нажимаю F7
     
     private void DG_test_SelectionChanged(object sender, SelectionChangedEventArgs e)
        {
            InitializeComponent();
            DGStaff.ItemsSource = SchoolEntities.GetContext().Staff.ToList(); (Staff - это название таблицы)
        }
           
        Переход по страницам
           UserWindow newForm = new UserWindow();
           newForm.Show();
           Сlose();
      
         Переход по страницам, если окно находится в папке Pages
           Pages.UserWindow newForm = new Pages.UserWindow();
           newForm.Show();
           Сlose();
           
           
         Git в случае возникновения ошибки при git push писать команды:
           git fetch
           git pull
           git push
           
           Внешний вид выпадающего списка
           <ComboBox Width="100" Height="30">
                <TextBlock>От А до Я</TextBlock>
                <TextBlock>По убыванию</TextBlock>
                <TextBlock>По возрастанию</TextBlock>
            </ComboBox>
