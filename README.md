Başlık - "C# .Net Framework Windows Forms App" ile Media Player uygulaması.

Microsoft Visual Studio ile basit bir Media Player uygulaması yaptım. İçinde olan özellikler - Browse button, Play button, Stop button, Resume button, << (fast reverse), >> (fast forward). 1 tane Label, 1 tane TextBox.

Şimdi görsel taraflarını bir-bir anlatacağım. Ama ilk önce bunu yapmalısınız.
Microsoft Visual Studio - Windows Forms App "C#" .Net seçmeniz lazım.

1. Toolbox-a Media Player yazarak onu buluyoruz. Daha sonra Media Player-in üzerine çift tıkladıkdan sonra yapacağımız Forms-a ekleniyor.
2. Media Player-i kendi isteğimize göre boyutlarını ayarlıyoruz. Ben Size (ölçü) olarak 1011:685 şeklinde yaptım. Location (konum) olarak ise -2:65 yaptım. Properties kısmında Anchor özelliğini Top, Bottom, Left, Right olarak ayarlıyoruz. Böylece uygulamanı büyük ekranda açtığımızda Media Player-in kendisi de büyüyecek.
3. Toolbox-a Label yazarak aratıyoruz ve Label-i kendi formumuza ekliyoruz. Label-in ismini Properties (ayarlar) kısmında olan Text özelliğinde değiştirerek Audio/Video yapıyoruz.
4. Properties kısmında yazdığımız Audio/Video yazısının Font-unu Sitka-Bonner Bold ve ölçüsünü 10 seçiyoruz. Background color olarak "Menu" seçiyoruz. ForeColor-u "ControlText" seçiyoruz. Anchor özelliğini Top,Left olarak ayarlıyoruz. Text Align özelliğinde MiddleCenter-i seçiyoruz.

Tüm bu ayarları yaptığımızda yazacağımız yazı Sitka Bonner Bold fontu ile, 10 ölçüyle, arka fon Menu renginde, kutucuğun ortasında olacak. Kutucuk uygulamada yukarı sol tarafda yer alacak.

Önemli Not: 4-cü addımı tüm diger yazılara da uyguluyoruz.

5. Toolbox-a TextBox yazarak aratıyoruz ve Textbox-u kendi formumuza ekliyoruz. Ölçüsünü ve yerini ayarladıkdan sonra diger özelliklerini uyguluyoruz (ForeColor, Background Color, Font, TextAlign, Anchor)
6. ToolBox-a Button yazarak aratıyoruz ve Button-u kendi formumuza ekliyoruz. Properties kısmında Text özelliğinde button-umuzun ismini Browse olarak yazıyoruz. Button-un ölçüsü 97:37 olacak şekilde ayarlıyoruz. Location olarak ise 316:12 şeklinde yapıyoruz. Bunları ayarladıkdan sonra diger özelliklerini uyguluyoruz (ForeColor, Background Color, Font, TextAlign, Anchor).
7. Toolbox-a daha bir Button yazarak aratıyoruz ve Button-u kendi formumuza ekliyoruz. Properties kısmında Text özelliğinde button-umuzun ismini Play olarak yazıyoruz. Button-un ölçüsü 90:37 olacak şekilde ayarlıyoruz. Location olarak ise 419:12 şeklinde yapıyoruz. Bunları ayarladıkdan sonra diger özelliklerini uyguluyoruz (ForeColor, Background Color, Font, TextAlign, Anchor).
8. Toolbox-a daha bir Button yazarak aratıyoruz ve Button-u kendi formumuza ekliyoruz. Properties kısmında Text özelliğinde button-umuzun ismini Stop olarak yazıyoruz. Button-un ölçüsü 87:37 olacak şekilde ayarlıyoruz. Location olarak ise 515:12 şeklinde yapıyoruz. Bunları ayarladıkdan sonra diger özelliklerini uyguluyoruz (ForeColor, Background Color, Font, TextAlign, Anchor)
9. Toolbox-a daha bir Button yazarak aratıyoruz ve Button-u kendi formumuza ekliyoruz. Properties kısmında Text özelliğinde button-umuzun ismini Pause olarak yazıyoruz. Button-un ölçüsü 87:37 olacak şekilde ayarlıyoruz. Location olarak ise 608:12 şeklinde yapıyoruz. Bunları ayarladıkdan sonra diger özelliklerini uyguluyoruz (ForeColor, Background Color, Font, TextAlign, Anchor).
10. Toolbox-a daha bir Button yazarak aratıyoruz ve Button-u kendi formumuza ekliyoruz. Properties kısmında Text özelliğinde button-umuzun ismini Resume olarak yazıyoruz. Button-un ölçüsü 86:37 olacak şekilde ayarlıyoruz. Location olarak ise 701:12 şeklinde yapıyoruz. Bunları ayarladıkdan sonra diger özelliklerini uyguluyoruz (ForeColor, Background Color, Font, TextAlign, Anchor).
11. Toolbox-a daha bir Button yazarak aratıyoruz ve Button-u kendi formumuza ekliyoruz. Properties kısmında Text özelliğinde button-umuzun ismini << olarak yazıyoruz. Button-un ölçüsü 85:37 olacak şekilde ayarlıyoruz. Location olarak ise 798:12 şeklinde yapıyoruz. Bunları ayarladıkdan sonra diger özelliklerini uyguluyoruz (ForeColor, Background Color, Font, TextAlign, Anchor).
12. Toolbox-a daha bir Button yazarak aratıyoruz ve Button-u kendi formumuza ekliyoruz. Properties kısmında Text özelliğinde button-umuzun ismini >> olarak yazıyoruz. Button-un ölçüsü 85:37 olacak şekilde ayarlıyoruz. Location olarak ise 878:12 şeklinde yapıyoruz. Bunları ayarladıkdan sonra diger özelliklerini uyguluyoruz (ForeColor, Background Color, Font, TextAlign, Anchor).
13. Form-umuzun kendi görsel taraflarından bahsedelim. Form-un ölçüsü 1032:81 olacak şekilde ayarlıyoruz. Properties kısmında StartPosition özellğini Manual olarak ayarlıyoruz. İcon kısmında İcon-u Media Player-in kendi iconu olarak ayarılıyoruz. BackgroundColor-u ControlLight olarak ayarlıyoruz. Ve form-muzun ismini Media Player yazıyoruz.
14. En önemli olan Toolbox-a OpenFileDialog yazarak aratıyoruz ve OpenFileDialog-u kendi formumuza ekliyoruz. Bu özellik sayeseinde bilgisayardakı audio ve videolara ulaşabiliriz.

Gelelim Kod kısmına. Yazacağımız kodlar çok az ve benzer olacak.

1. Button 1 yani Browse-a ait olan kod kısmına bu kodu yazıyoruz.
 OpenFileDialog opf = new OpenFileDialog();
            if (opf.ShowDialog() == DialogResult.OK)
            {
                textBox1.Text = opf.FileName;
            }
Böylece Browse button-u aktif hale geliyor ve bilgisiyardakı audio ve videolara ulaşabiliyor.

2. Button 2 yani Play-a ait olan kod kısmına bu kodu yazıyoruz.
axWindowsMediaPlayer1.URL = textBox1.Text;
axWindowsMediaPlayer1.Ctlcontrols.play();
Böylece Play button-u aktif hale geliyor ve audio/video-nu başlata biliyor.

3. Button 3 yani Stop-a ait olan kod kısmına bu kodu yazıyoruz.
axWindowsMediaPlayer1.Ctlcontrols.stop();
Böylece Stop button-u aktif hale geliyor ve audio/video-nu durdura biliyor.

4. Button 4 yani Pause-a ait olan kod kısmına bu kodu yazıyoruz.
axWindowsMediaPlayer1.Ctlcontrols.pause();
Böylece Pause button-u aktif hale geliyor ve audio/video-nu duraklata biliyor.

5. Button 5 yani Resume-a ait olan kod kısmına bu kodu yazıyoruz.
axWindowsMediaPlayer1.Ctlcontrols.play();
Böylece Resume button-u aktif hale geliyor ve audio/video-nu devam ettiriyor.

6. Button 6 yani Fast Reverse (<<)-a ait olan kod kısmına bu kodu yazıyoruz.
axWindowsMediaPlayer1.Ctlcontrols.fastreverse();
Böylece Fast Reverse button-u aktif hale geliyor ve audio/video-nu hızlı şekilde geri sarıyor.

7. Button 7 yani Fast Forward (>>)-a ait olan kod kısmına bu kodu yazıyoruz.
axWindowsMediaPlayer1.Ctlcontrols.fastforward();
Böylece Fastforward button-u aktif hale geliyor ve audio/video-nu hızlı şekilde ileri sarıyor.
