---
title: 'Nasıl yapılır: Windows Forms StatusBar Denetiminde Hangi Panele Tıklandığını Belirleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], determining panel clicked
- panels [Windows Forms], determining clicked
- StatusBar control [Windows Forms], coding panel click events
- StatusBar control [Windows Forms], determining panel clicked
- PanelClick event [Windows Forms], determining panel clicked
- Panel control [Windows Forms], determining click
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
ms.openlocfilehash: b83dc7273c612e914840307bc749abef780284ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527980"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>Nasıl yapılır: Windows Forms StatusBar Denetiminde Hangi Panele Tıklandığını Belirleme
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip> Ve <xref:System.Windows.Forms.ToolStripStatusLabel> denetimleri değiştirin ve işlevsellik eklemek <xref:System.Windows.Forms.StatusBar> ve <xref:System.Windows.Forms.StatusBarPanel> denetler; ancak, <xref:System.Windows.Forms.StatusBar> ve <xref:System.Windows.Forms.StatusBarPanel> denetimleri korunur geriye dönük uyumluluk ve gelecekte kullanım için ise, ' ı seçin.  
  
 Programa [StatusBar denetimi](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) kullanıcı tıklamalarına yanıt verme, içindeki case deyimi kullanın denetim <xref:System.Windows.Forms.StatusBar.PanelClick> olay. Olayı tıklatılan başvuru içeren bir değişken (paneli değişken) içeren <xref:System.Windows.Forms.StatusBarPanel>. Bu başvuru kullanarak tıklatılan paneli dizinini belirlemek ve buna göre program.  
  
> [!NOTE]
>  Emin <xref:System.Windows.Forms.StatusBar> denetimin <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> özelliği ayarlanmış `true`.  
  
### <a name="to-determine-which-panel-was-clicked"></a>Hangi panele tıklandığını belirleme  
  
1.  İçinde <xref:System.Windows.Forms.StatusBar.PanelClick> olay işleyicisi, kullanım bir `Select Case` (Visual Basic'te) veya `switch case` (Visual C# veya [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) deyimi olay değişkenlerini tıklatılan panelinde dizinini inceleyerek hangi panele tıklandığını belirleme.  
  
     Varlığı formunda, aşağıdaki kod örneğinde gerektiren bir <xref:System.Windows.Forms.StatusBar> denetimi `StatusBar1`ve iki <xref:System.Windows.Forms.StatusBarPanel> nesneleri `StatusBarPanel1` ve `StatusBarPanel2`.  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,   
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
     (Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) formun oluşturucuda olay işleyicisi kaydetmek için aşağıdaki kodu yerleştirin.  
  
    ```csharp  
    this.statusBar1.PanelClick += new   
       System.Windows.Forms.StatusBarPanelClickEventHandler   
       (this.statusBar1_PanelClick);  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [Nasıl yapılır: Durum Çubuğu Panellerinin Boyutunu Ayarlama](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)  
 [İzlenecek yol: Çalışma Zamanında Durum Çubuğu Bilgilerini Güncelleştirme](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)  
 [StatusBar Denetimine Genel Bakış](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
