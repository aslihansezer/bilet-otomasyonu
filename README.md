bilet-otomasyonu
================

bilet otomasyonu projesi

#include <graphics.h>
#include<conio.h>

int sayfa=0,goster=0,x,x1,y1,y,bilets=0,sayac=0,seferkoltuk[33],nereden=9,nereye=9,seferdolu[33],sefercins[33],sayfa1,starih=9;
char isim[20]="x",soyisim[20]="x",telefon[20]="x",cinsiyet[20]="x";
char isim1[20][20],soyisim1[20][20],telefon1[20][20],cinsiyet1[20][20];
 int dizix[40],diziy[40];
int koltukno[20];
//SEFER OKU FONKSİYONU
void bilgigoster()
{
      FILE *dg;
      char isimm[20],telefonn[20],cinsiyett[20],neredenn[20],nereyee[20],koltukkk[20],tarih11[20] ;
      int koltukk=0,tarih1=0;    
      if( (dg=fopen("yolcular.txt","r")) == NULL )         puts("Dosya açılmadı !\n"), exit(1);
       
       
       while(!feof(dg))              
       {
       fscanf(dg,"%s %s %s %s %s %s %s",isimm,telefonn,cinsiyett,tarih11,neredenn,nereyee,koltukkk); 
       
       // eğer mouse koordinatları koltuk koordinatları üzerindeyse ve koltuk numarası doluysa o koltuğa dair yolcular.txt
       // dosyasındaki bilgiler ekrana yazdırılır.
            for(int k=1;k<33;k++)
            if(x1>dizix[k]&&x1<dizix[k]+30&&y1>diziy[k]&&y1<diziy[k]+30)
            {                                                      
                    if(atoi(koltukkk)==k&&sayfa1==atoi(tarih11))
                     {  
                        outtextxy(780,200,"İsim: ");                          
                        outtextxy(840,200,isimm);
                        outtextxy(780,220,"Telefon: ");                        
                        outtextxy(840,220,telefonn);
                        outtextxy(780,240,"Cinsiyet: ");
                        if(cinsiyett[0]=='0')
                        outtextxy(840,240,"Bayan");
                        else
                        outtextxy(840,240,"Bay");
                        outtextxy(780,260,"Nereden: ");
                        outtextxy(780,280,"Nereye: ");
                        if(neredenn[0]=='1')
                        outtextxy(840,260,"Kocaeli");
                        if(neredenn[0]=='2')
                        outtextxy(840,260,"Bursa");
                        if(neredenn[0]=='3')
                        outtextxy(840,260,"Balıkesir");
                        if(neredenn[0]=='4')
                        outtextxy(840,260,"Manisa");
                        if(neredenn[0]=='5')
                        outtextxy(840,260,"İzmir");
                        if(nereyee[0]=='1')
                        outtextxy(840,280,"Kocaeli");
                        if(nereyee[0]=='2')
                        outtextxy(840,280,"Bursa");
                        if(nereyee[0]=='3')
                        outtextxy(840,280,"Balıkesir");
                        if(nereyee[0]=='4')
                        outtextxy(840,280,"Manisa");
                        if(nereyee[0]=='5')
                        outtextxy(840,280,"İzmir");
                     
                     }
                    
        } 
         else
         {                        
         }
        
   }   
   fclose(dg);   
}

void seferoku()
{
       FILE *dg;
       //seçilen tarihe göre sefer.txt açılır
       int koltuk,dolu,cins,i=1;
       if(sayfa1==1)
       {
         if( (dg=fopen("sefer1.txt","r")) == NULL )         puts("Dosya açılmadı !\n"), exit(1);
       }
       if(sayfa1==2)
       {
        if( (dg=fopen("sefer2.txt","r")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
       }  
       if(sayfa1==3)
       {
        if( (dg=fopen("sefer3.txt","r")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
       }
      if(sayfa1==4)
       {
        if( (dg=fopen("sefer4.txt","r")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
       }
      if(sayfa1==5)
       {
        if( (dg=fopen("sefer5.txt","r")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
       }
      if(sayfa1==6)
       {
        if( (dg=fopen("sefer6.txt","r")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
       }
      if(sayfa1==7)
       {
        if( (dg=fopen("sefer7.txt","r")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
       }
      if(sayfa1==8)
       {
        if( (dg=fopen("sefer8.txt","r")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
       }
      if(sayfa1==9)
       {
        if( (dg=fopen("sefer9.txt","r")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
       }
      if(sayfa1==10)
       {
        if( (dg=fopen("sefer10.txt","r")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
       }
     
     
      // seferdeki doluluk ve cinsiyetleri diziye atılır.
  for(int y=0;y<32;y++)            
   {
      fscanf(dg,"%d %d %d",&koltuk,&dolu,&cins); 
      seferkoltuk[i]=koltuk;
      seferdolu[i]=dolu;
      sefercins[i]=cins;
      i++;
   }
   
}


//SEFER  GOSTER FONKSİYONU
void sefergoster()
{
          int kixy=40,ikxy=270;
          setcolor(14);
          outtextxy(30,150,"NEREDEN"); 
          setcolor(3);   
          outtextxy(30,170,"KOCAELİ"); 
          outtextxy(30,190,"BURSA"); 
          outtextxy(30,210,"BALIKESİR"); 
          outtextxy(30,230,"MANİSA"); 
          outtextxy(30,250,"İZMİR");                  
          setcolor(14);
          outtextxy(175,150,"NEREYE");
          setcolor(3);
          outtextxy(175,170,"KOCAELİ");
          outtextxy(175,190,"BURSA");
          outtextxy(175,210,"BALIKESİR");
          outtextxy(175,230,"MANİSA");
          outtextxy(175,250,"İZMİR");
          setcolor(14);
          outtextxy(300,150,"TARİH");
          setcolor(14);
          outtextxy(425,150,"BILET SAYISI");
          
}


// IKINCI SAYFA FONSKIYONU
 int ikincisayfa()
    {
    
    dizix[1]=200;    diziy[1]=20;
    dizix[2]=200;    diziy[2]=60;
    dizix[3]=200;    diziy[3]=150;
    dizix[4]=200;    diziy[4]=190;
    dizix[5]=250;    diziy[5]=20;
    dizix[6]=250;    diziy[6]=60;
    dizix[7]=250;    diziy[7]=150;
    dizix[8]=250;    diziy[8]=190;
    dizix[9]=300;    diziy[9]=20;
    dizix[10]=300;    diziy[10]=60;
    dizix[11]=300;    diziy[11]=150;
    dizix[12]=300;    diziy[12]=190;
    dizix[13]=350;    diziy[13]=20;
    dizix[14]=350;    diziy[14]=60;
    dizix[15]=350;    diziy[15]=150;
    dizix[16]=350;    diziy[16]=190;
    dizix[17]=400;    diziy[17]=20;
    dizix[18]=400;    diziy[18]=60;
    dizix[19]=400;    diziy[19]=150;
    dizix[20]=400;    diziy[20]=190;
    dizix[21]=450;    diziy[21]=20;
    dizix[22]=450;    diziy[22]=60;
    dizix[23]=450;    diziy[23]=150;
    dizix[24]=450;    diziy[24]=190;
    dizix[25]=500;    diziy[25]=20;
    dizix[26]=500;    diziy[26]=60;
    dizix[27]=500;    diziy[27]=150;
    dizix[28]=500;    diziy[28]=190;
    dizix[29]=550;    diziy[29]=20;
    dizix[30]=550;    diziy[30]=60;
    dizix[31]=550;    diziy[31]=150;
    dizix[32]=550;    diziy[32]=190;
    
    int sur = DETECT, gmod;
    int biletno=0;
    settextstyle(12, 0, 1); 
    readimagefile("otobus.jpg",10,10,1000,240);
    while(sayfa==1)
    {
                   while(ismouseclick(WM_MOUSEMOVE))
                   {
                       getmouseclick(WM_MOUSEMOVE,x1,y1);
                       // koltuk bilgilerinde dolu koltukların üzerine gelindiğinde koltuk bilgileri gösterilir.
                       bilgigoster();  
                   }
      
      
                   while(ismouseclick(WM_LBUTTONDOWN))
                   {
                       getmouseclick(WM_LBUTTONDOWN,x,y);
        //geri butonu
                   if(x>450&&x<490&&y>400&&y<440)
                   {                             
                       sayfa=0;
                       goster=0;
                   }
        //ileri butonu
                   if(x>500&&x<540&&y>400&&y<440)
                   {                             
                       sayfa=2;
                       goster=0;
                   }  
                   if(x>20&&x<90&&y>350&&y<370)
                   {
                                               
                       printf("isim gir");
                       scanf("%s",&isim);
                       outtextxy(150,350,isim);   
                   }  
         
                   if(x>20&&x<90&&y>375&&y<395)
                   {
                       printf("telefonu gir");
                       scanf("%s",&telefon);
                       outtextxy(150,375,telefon);   
                   }  
                   if(x>110&&x<130&&y>400&&y<420)
                   {
                       cinsiyet[0]='1';
           
                   }  
                   if(x>135&&x<170&&y>400&&y<420)
                   {
                       cinsiyet[0]='0';
           
                   }  
                   seferoku();
                   // seferoku fonksiyonununda oluşturduğumuz dizi bu bölümde kullanılır
                   // seferdeki doluluk veya cinsyete göre koltukların rengi belli olur.
                   for(int l=1;l<33;l++)
        { 
        if(l%2==1)
        {
            if(seferdolu[l]==1&&seferdolu[l+1]==1)
            {
                     readimagefile("siyah.jpg",dizix[l+1],diziy[l+1],dizix[l+1]+30,diziy[l+1]+30);
                     readimagefile("siyah.jpg",dizix[l],diziy[l],dizix[l]+30,diziy[l]+30);                               
            }
            else if(seferdolu[l]==0&&seferdolu[l+1]==0)
            {
                     readimagefile("yesil.jpg",dizix[l+1],diziy[l+1],dizix[l+1]+30,diziy[l+1]+30);
                     readimagefile("yesil.jpg",dizix[l],diziy[l],dizix[l]+30,diziy[l]+30);            
            }
            else if(seferdolu[l]==0&&seferdolu[l+1]==1)
            {
                           if(sefercins[l+1]==0)
                           {
                     readimagefile("siyah.jpg",dizix[l+1],diziy[l+1],dizix[l+1]+30,diziy[l+1]+30);
                     readimagefile("pembe.jpg",dizix[l],diziy[l],dizix[l]+30,diziy[l]+30);                       
                           }  
                           else
                           {
                     readimagefile("siyah.jpg",dizix[l+1],diziy[l+1],dizix[l+1]+30,diziy[l+1]+30);
                     readimagefile("mavi.jpg",dizix[l],diziy[l],dizix[l]+30,diziy[l]+30);   
                           }   
            }
            else if(seferdolu[l]==1&&seferdolu[l+1]==0)
            {
                           if(sefercins[l]==0)
                           {
                     readimagefile("pembe.jpg",dizix[l+1],diziy[l+1],dizix[l+1]+30,diziy[l+1]+30);
                     readimagefile("siyah.jpg",dizix[l],diziy[l],dizix[l]+30,diziy[l]+30);                       
                           } 
                            else
                           {
                     readimagefile("mavi.jpg",dizix[l+1],diziy[l+1],dizix[l+1]+30,diziy[l+1]+30);
                     readimagefile("siyah.jpg",dizix[l],diziy[l],dizix[l]+30,diziy[l]+30);   
                           }     
            }
        }
    
   }
      
        
   
   // koltukların içine numaralar yazdırılır.
       for(int k=1;k<33;k++)
       {
   
       char b[3];
       for(int y=0;y<33;y++)
       {
       setcolor(15);
        sprintf(b,"%d",k);
        outtextxy(dizix[k]+10,diziy[k]+5,b);          
       }
       
        if(x>dizix[k]&&x<dizix[k]+30&&y>diziy[k]&&y<diziy[k]+30)
        {                                                      
        biletno=k;
        setcolor(12);
        outtextxy(30,300,"Bilet No:");
        }
       }
     
    char a[30],sayacs[3];
    
    // bilet sayına göre veri girilir.
     if(bilets!=sayac)
      {
           sprintf(sayacs,"%d",sayac+1);
           outtextxy(30,320,"                                                                           "); 
           outtextxy(90,300,"                                                                     ");
           outtextxy(90,320,sayacs);   
           outtextxy(30,320,"Lütfen ");  
           outtextxy(100,320,". yolcunun bilgilerini giriniz ");      
   
 
   
           if(isim[0]!='x'&&telefon[0]!='x'&&cinsiyet[0]!='x')
            {
            outtextxy(30,320,"                                                                      "); 
            outtextxy(30,320,"artık koltuk seçebilirsiniz");    
            printf("%s",isim);
            for(int i=1;i<33;i++)
            if(biletno==i)
            {
                    setcolor(15);
                    sprintf(a,"%d numarali koltugu sectiniz",i);
                    outtextxy(90,300,a);
                        
                    setcolor(15);
          sprintf( isim1[sayac],"%s",isim);   
          sprintf(telefon1[sayac],"%s",telefon); 
          sprintf( cinsiyet1[sayac],"%s",cinsiyet);
          koltukno[sayac]=biletno;
          printf("\n---%d---",biletno);
          if(biletno%2==1)
          {
              if(seferdolu[biletno]==1)
              { 
              outtextxy(30,320,"Dolu Koltuk Seçilemez!            ");  
              /*
              */
              }
              if(seferdolu[biletno]==0)
              { 
                  if(seferdolu[biletno+1]==0)
                  { 
                  
                  outtextxy(30,320,"Koltuk Uygun!                        ");
                  sayac++;
                      
                      
                  isim[0]='x';
                  telefon[0]='x';
                  cinsiyet[0]='x';
                  outtextxy(150,375,"                    ");   
                  outtextxy(150,350,"                      ");    
                  }
                  else
                  {
                      if(sefercins[biletno+1]==0&&  cinsiyet[0]=='0')
                       { 
                              outtextxy(30,320,"Koltuk Uygun!                     "); 
                              sayac++;
              isim[0]='x';
              telefon[0]='x';
              cinsiyet[0]='x';
              outtextxy(150,375,"                    ");   
              outtextxy(150,350,"                      ");                    
                       }
                       else if(sefercins[biletno+1]==1&&  cinsiyet[0]=='1')
                       {
                            outtextxy(30,320,"Koltuk Uygun!                          "); 
                            sayac++;
                            isim[0]='x';
                            telefon[0]='x';
                            cinsiyet[0]='x';
                            outtextxy(150,375,"                    ");   
                            outtextxy(150,350,"                      ");    
                       }
                       else
                       {
                            outtextxy(30,320,"Koltuk Uygun Değil!             ");    
                       }
                       
                      
                  }
              }
            
          }
          
          
          
            if(biletno%2==0)
          {
              if(seferdolu[biletno]==1)
              { 
              outtextxy(30,320,"Dolu Koltuk Seçilemez!");  
              /*
              */
              }
              if(seferdolu[biletno]==0)
              { 
                  if(seferdolu[biletno-1]==0)
                  { 
                  outtextxy(30,320,"Koltuk Uygun!                     ");
                  sayac++;
                  isim[0]='x';
                  telefon[0]='x';
                  cinsiyet[0]='x';
                  outtextxy(150,375,"                    ");   
                  outtextxy(150,350,"                      ");  
                  }
                  else
                  {
                      if(sefercins[biletno-1]==0&&  cinsiyet[0]=='0')
                       { 
                              outtextxy(30,320,"Koltuk Uygun!               "); 
                              sayac++;
                              isim[0]='x';
                              telefon[0]='x';
                              cinsiyet[0]='x';
                              outtextxy(150,375,"                    ");   
                              outtextxy(150,350,"                      ");                    
                       }
                       else if(sefercins[biletno-1]==1&&  cinsiyet[0]=='1')
                       {
                            outtextxy(30,320,"Koltuk Uygun!             "); 
                            sayac++;
                            isim[0]='x';
                            telefon[0]='x';
                            cinsiyet[0]='x';
                            outtextxy(150,375,"                    ");   
                            outtextxy(150,350,"                      ");    
                       }
                       else
                       {
                            outtextxy(30,320,"Koltuk Uygun Değil!               ");    
                       }
                       
                      
                  }
              }
              
              
              
          }
          
          
          
          }                                                                 
                                                                       
   }
   
    biletno=0;
    } 
    else
    {
      
      
      }
          
      }
      readimagefile("yesil.jpg",750,20,780,50);
      setcolor(12);
      outtextxy(780,25," :Bos Koltuk");
      
      readimagefile("siyah.jpg",750,55,780,85);
      setcolor(12);
      outtextxy(780,60," :Dolu Koltuk");
      
      readimagefile("pembe.jpg",750,90,780,120);
      setcolor(12);
      outtextxy(780,95," :Sadece Bayanlar Icin  ");
      
      readimagefile("mavi.jpg",750,125,780,155);
      setcolor(12);
      outtextxy(780,130," :Sadece Baylar Icin ");
      
      outtextxy(30,350," Ad Soyad:");
      outtextxy(30,375," Cep Telefonu:");
      outtextxy(30,400," Cinsiyet: Bay Bayan");
      
      readimagefile("satinal.jpg",750,350,815,390);
      
}
  
 }    
 
 
 
 
 //UCUNCU SAYFA
 int goster3=0;
 int ucuncusayfa()
{
   
    while(ismouseclick(WM_LBUTTONDOWN))
    {
        getmouseclick(WM_LBUTTONDOWN,x,y);
        // geri butonu
        if(x>450&&x<490&&y>400&&y<440)
        {                             
         sayfa=0;
         goster=0;
        }
    }
    if(goster3==0)
    
    {
                  //sefer.txt güncellenmesi ve  yolcuların bilgisi bu sayfa yapılmaktadır.
                 
                      isim[0]='x',soyisim[0]='x',telefon[0]='x',cinsiyet[0]='x';
                    //  printf("\n%d %d %d\n",nereden,nereye,bilets);
                      outtextxy(30,90,"Yolcu(lar) Başarıyla Eklenmiştir. ");
                      outtextxy(30,110,"Yeni işlem için geri butonuna basınız... ");
  
              FILE *dg,*dg1;
               if( (dg1=fopen("yolcular.txt","a")) == NULL )         puts("Dosya açılmadı !\n"), exit(1);
               int koltuk,dolu,cins,i=1;
               if(sayfa1==1)
               {
                  if( (dg=fopen("sefer1.txt","w")) == NULL )         puts("Dosya açılmadı !\n"), exit(1);
               }
               if(sayfa1==2)
               {
                  if( (dg=fopen("sefer2.txt","w")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
               }  
               if(sayfa1==3)
               {
                   if( (dg=fopen("sefer3.txt","w")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
               }
               if(sayfa1==4)
               {
                   if( (dg=fopen("sefer4.txt","w")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
               }
               if(sayfa1==5)
               {
                   if( (dg=fopen("sefer5.txt","w")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
               }
              if(sayfa1==6)
               {
                   if( (dg=fopen("sefer6.txt","w")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
               }
              if(sayfa1==7)
               {
                   if( (dg=fopen("sefer7.txt","w")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
               }
              if(sayfa1==8)
               {
                   if( (dg=fopen("sefer8.txt","w")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
               }
              if(sayfa1==9)
               {
                   if( (dg=fopen("sefer9.txt","w")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
               }
              if(sayfa1==10)
               {
                   if( (dg=fopen("sefer10.txt","w")) == NULL )     puts("Dosya açılmadı !\n"), exit(1);
               }
   
              // sefer.txt deki güncelleme işlemi bu bölümde yapılır.
          for(int k=1;k<33;k++)              
           {
                                  
  
                  if(koltukno[0]==k)
                  {
                     fprintf(dg,"%d %s %s\n",k, "1",cinsiyet1[0]);
                     //ad tel cins tarih  nereden nereye koltuk seferkodu 
                     fprintf(dg1,"%s %s %s %d %d %d %d\n",isim1[0],telefon1[0],cinsiyet1[0],sayfa1,nereden,nereye,k,sayfa1);                     
                  }
                  else if(koltukno[1]==k)
                  {
                     fprintf(dg,"%d %s %s\n",k, "1",cinsiyet1[1]);   
                     fprintf(dg1,"%s %s %s %d %d %d %d\n",isim1[1],telefon1[1],cinsiyet1[1],sayfa1,nereden,nereye,k,sayfa1);                   
                  }
                  else if(koltukno[2]==k)
                  {
                     fprintf(dg,"%d %s %s\n",k, "1",cinsiyet1[2]);   
                     fprintf(dg1,"%s %s %s %d %d %d %d\n",isim1[2],telefon1[2],cinsiyet1[2],sayfa1,nereden,nereye,k,sayfa1);                   
                  }
                  else if(koltukno[3]==k)
                  {
                     fprintf(dg,"%d %s %s\n",k, "1",cinsiyet1[3]);  
                     fprintf(dg1,"%s %s %s %d %d %d %d\n",isim1[3],telefon1[3],cinsiyet1[3],sayfa1,nereden,nereye,k,sayfa1);                    
                  }
                  else
                  {
                     fprintf(dg,"%d %d %d\n",k,seferdolu[k],sefercins[k]);      
                  }
           }
             fclose(dg);
             printf("\n%s - %s - %s - %d - %d",isim1[i],telefon1[i],cinsiyet1[i],sayfa1, koltukno[i]);   
             //anamenüye döndüğümüz için programda kullanılacak değişkenler sıfırlanır
               
             goster=0,bilets=0,sayac=0,nereden=9,nereye=9,starih=9;
   
    goster3=1;
}
}
int main() 
{  
    // 1. Sayfadaki seferler.txt'deki verileri kullanabilmemiz için tanımladığımız değişkenler
    FILE *dg; 
    int k=0,art=170;
    char  seferler[10],tarih[15],saat[10],kapasite[10],yer[10],biletss[2];
    char  seferler1[10][10],tarih1[15][10],saat1[10][10],kapasite1[10][10],yer1[10][10];
  
    int sur = DETECT, gmod;
    char say1[5],say2[5];

     /* grafik ekranını başlat */
    initwindow(1000,500);
    // Sayfalama mantığının başladığı yer
    // 1. sayfanın döngü koşulu
    while(sayfa==0) 
    {
      goster3=0;
      // goster değşkenleri arkaplanda resimlerin sürekli yenilenmesini engellemek amaçlı yapıldı.
     if(goster==0)
     {
     readimagefile("arka.jpg",0,0,1000,500);
     setcolor(12);
     outtextxy(30,90,"KOCAELİ-İZMİR SEFERLERİ");
     outtextxy(30,300,"Nereden: ");
     outtextxy(30,325,"Nereye: ");
     outtextxy(30,350,"Tarih: ");
     outtextxy(30,375,"Bilet Sayısı: ");
     sefergoster();
     goster=1;
     }
    
    art=170;
    // mouse tıklama komutları. x ve y değişkenlerinde koordinatlar tutulur.
    while(ismouseclick(WM_LBUTTONDOWN))
    {
    getmouseclick(WM_LBUTTONDOWN,x,y);
    sprintf(say1,"x:%d",x);
    sprintf(say2,"y:%d",y);
       if(x>30&&x<100&&y>170&&y<180)
         {
             nereden=1;
             outtextxy(90,300,"                             ");
             outtextxy(90,300,"Kocaeli");
         }
      if(x>30&&x<100&&y>190&&y<200)
         {
             nereden=2;
             outtextxy(90,300,"                                 ");
             outtextxy(90,300,"Bursa");
         }
      if(x>30&&x<100&&y>210&&y<220)
         {
             nereden=3;
             outtextxy(90,300,"                                 ");
             outtextxy(90,300,"Balikesir");
         }
      if(x>30&&x<100&&y>230&&y<240)
         {
             nereden=4;
             outtextxy(90,300,"                                 ");
             outtextxy(90,300,"Manisa");
         }
      if(x>30&&x<100&&y>250&&y<260)
         {
             nereden=5;
             outtextxy(90,300,"                                 ");
             outtextxy(90,300,"İzmir");
         }
      if(x>175&&x<245&&y>170&&y<180)
         {
             nereye=1;
             outtextxy(90,325,"                                 ");
             outtextxy(90,325,"Kocaeli");
         }
      if(x>175&&x<245&&y>190&&y<200)
         {
             nereye=2;
             outtextxy(90,325,"                                 ");
             outtextxy(90,325,"Bursa");
         }
      if(x>175&&x<245&&y>210&&y<220)
         {
             nereye=3;
             outtextxy(90,325,"                                 ");
             outtextxy(90,325,"Balikesir");
         }
      if(x>175&&x<245&&y>230&&y<240)
         {
             nereye=4;
             outtextxy(90,325,"                                 ");
             outtextxy(90,325,"Manisa");
         }
      if(x>175&&x<245&&y>250&&y<260)
         {
             nereye=5;
             outtextxy(90,325,"                                 ");
             outtextxy(90,325,"İzmir");
         }
      if(x>300&&x<370&&y>170&&y<190)
         {
             starih=1;
             outtextxy(90,350,"                             ");
             outtextxy(90,350,"21.09.2013");
          }
      if(x>300&&x<370&&y>190&&y<200)
          {
             starih=2;
             outtextxy(90,350,"                             ");
             outtextxy(90,350,"22.09.2013");
          }
      if(x>300&&x<370&&y>210&&y<220)
          {
             starih=3;
             outtextxy(90,350,"                             ");
             outtextxy(90,350,"23.09.2013");
          }
      if(x>300&&x<370&&y>230&&y<240)
          {
             starih=4;
             outtextxy(90,350,"                             ");
             outtextxy(90,350,"24.09.2013");
          }
      if(x>300&&x<370&&y>250&&y<260)
          {
             starih=5;
             outtextxy(90,350,"                             ");
             outtextxy(90,350,"25.09.2013");
          }
    
    // Seçilen tarihe göre şehirlerin hangi saatte hareket ettiğini yazdırıyoruz.
    if(starih!=9)
    {
        if(nereden<nereye)
    {
        if(nereden==1)
            {
                        setcolor(9);
                        outtextxy(250,290,"Kocaeliden seçtiğiniz tarihte 09:00");
                        outtextxy(250,310,"saatinde sefer vardır.");
                        setcolor(14);
            }
        if(nereden==2)
            {
                        setcolor(9);
                        outtextxy(250,290,"Bursadan seçtiğiniz tarihte 11:00");
                        outtextxy(250,310,"saatinde sefer vardır.");
                        setcolor(14);
            }
        if(nereden==3)
            {
                       setcolor(9);
                       outtextxy(250,290,"Balıkesirden seçtiğiniz tarihte 13:00");
                       outtextxy(250,310,"saatinde sefer vardır.");
                       setcolor(14);
            }
        if(nereden==4)
            {
                       setcolor(9);
                       outtextxy(250,290,"Manisadan seçtiğiniz tarihte 15:00");
                       outtextxy(250,310,"saatinde sefer vardır.");
                       setcolor(14);
            }
    }   
    
    
       if(nereye<nereden)
    {
        if(nereden==5)
            {
                       setcolor(9);
                       outtextxy(250,290,"İzmirden seçtiğiniz tarihte 17:00");
                       outtextxy(250,310,"saatinde sefer vardır.");
                       setcolor(14);
            }
        if(nereden==4)
            {
                      setcolor(9);
                      outtextxy(250,290,"Manisadan seçtiğiniz tarihte 19:00");
                      outtextxy(250,310,"saatinde sefer vardır.");
                      setcolor(14);
            }
        if(nereden==3)
            {
                      setcolor(9);
                      outtextxy(250,290,"Balıkesirden seçtiğiniz tarihte 21:00");
                      outtextxy(250,310,"saatinde sefer vardır.");
                      setcolor(14);
            }
        if(nereden==2)
            {
                      setcolor(9);
                      outtextxy(250,290,"Bursadan seçtiğiniz tarihte 23:00");
                      outtextxy(250,310,"saatinde sefer vardır.");
                      setcolor(14);
            }
    }   
                 
    }
    // Şehirler aynı seçildiğinde uyarı verir.
    if(nereden==nereye&&nereden!=9)
    outtextxy(90,325,"Aynı şehir seçtiniz");
    else
    {
    if(nereden!=9&&nereye!=9)
    {
     // seferler.txt açılır ve dosya içindeki değerler değişkenlere ve dizilere aktarılır.
        if( (dg=fopen("seferler.txt","r")) == NULL )
        puts("Dosya açılmadı !\n"), exit(1);
        
        
     art=170;
     
    {
              
      fscanf(dg,"%s%s%s%s%s",&seferler,&tarih,&yer,&saat,&kapasite); /* verileri oku! */  
      
      if(nereden<nereye) 
      {
      
       sprintf( tarih1[k],"%s",tarih);
       sprintf( yer1[k],"%s",yer);
    
              if(yer1[k][0]=='1')
              {
                               
                 outtextxy(300,art,tarih1[k]);    
                 k++;
                 art=art+20; 
              }
      
      }
      else
      {
          // tarihlerin ekrana seçilen yerlere göre gösterilmesini sağlar.
          sprintf( tarih1[k],"%s",tarih);
          sprintf( yer1[k],"%s",yer);
         
          if(yer1[k][0]=='5')
           {
                outtextxy(300,art,tarih1[k]);
                k++;
                art=art+20;
            }
          }
     
          
     
      
   }    
    fclose(dg);                   
                             
    }
    
}
    // tarih seçilmişse bilet sayısı belirleme ekranı gösterilir.
     if(starih!=9)
      {
           outtextxy(110,375,"Lütfen Bilet Sayısını Belirleyiniz");
           readimagefile("p.jpg",425,170,465,210);  
           readimagefile("n.jpg",470,170,510,210);   
          
          if(x>425&&x<465&&y>170&&y<210)
     {
          if(bilets>=33)
          outtextxy(110,375,"En fazla 32 yolcu girilmelidir!               ");
          
          else
          {
              // bilet sayısı arttırma işlemi
                  bilets=bilets+1;
                  outtextxy(110,375,"                                                           ");
                  // sprintf int değişkenleri ekranda yazabilmemiz için string değişkene çevirir.
                  sprintf( biletss,"%d",bilets);
                  outtextxy(110,375,biletss);
}
          }   
      }
         if(x>470&&x<510&&y>170&&y<210)
      {
        if(bilets<1)
        outtextxy(110,375,"En az 1 yolcu girilmelidir!               ");
        else
        {
                  bilets=bilets-1;
                  outtextxy(110,375,"                                                           ");
                  sprintf( biletss,"%d",bilets);
                  outtextxy(110,375,biletss);
}
        }   
      //bilet sayısı belirleme işlemi bittiyse ileri butonu gösterilir.
        if(bilets>0)
        {
        readimagefile("ileri.jpg",500,400,540,440);          
        }  
      
      
        }
        // Eğer ileri butonu tıklandıysa  sayfa değişkenini 2. sayfa olarak ayarlarız
       if(x>500&&x<540&&y>400&&y<440)
        {
                                     
                                     
     sayfa=1;
     // sefer.txt dosyalarının hangi dosya açılacağı değişken belirlenir.
     if(nereden>nereye)
     {
                       printf("\n\n1-%d\n\n",starih);
                       if(starih==1)
                         sayfa1=1;
                       if(starih==2)
                         sayfa1=2;
                       if(starih==3)
                         sayfa1=3;
                       if(starih==4)
                         sayfa1=4;
                       if(starih==5)
                         sayfa1=5;
                       printf("\n\n1-%d\n\n",sayfa1);
     }
     else
     {
                       printf("\n\n2-%d\n\n",starih);
                       if(starih==1)
                         sayfa1=6;
                       if(starih==2)
                         sayfa1=7;
                       if(starih==3)
                         sayfa1=8;
                       if(starih==4)
                         sayfa1=9;
                       if(starih==5)
                         sayfa1=10;
                       printf("\n\n2-%d\n\n",sayfa1);
         
         }
     
      }
      
     int goster1=0,goster2=0;
     // 2. sayfanın döngüsü
     while(sayfa==1)
    {
         if(goster1==0)
         {           
          readimagefile("arka.jpg",0,0,1000,500);
          readimagefile("g.jpg",450,400,490,440);    
          readimagefile("ileri.jpg",500,400,540,440);       
          goster1=1;
          
         }
         // ikinci sayfadaki fonksiyonu    
         ikincisayfa();
           
    }
      while(sayfa==2)
    {
                    
         if(goster2==0)
         {
          printf("a" );       
          readimagefile("arka.jpg",0,0,1000,500);
          readimagefile("g.jpg",450,400,490,440);    
          readimagefile("ileri.jpg",500,400,540,440);       
          goster2=1;
          
         }  
          ucuncusayfa();  
           
    }
    k=0;
    }
    
    
        while(!kbhit()); //kalvyede herhangi bir tuşa basılıp basılmadığını kontrol eder.
        closegraph(); //close graphics window
        return 0;  
getch();
}
