---
title: Sada nástrojů prvku vytvoření Windows Forms. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- winforms
- toolbox
- windows forms
ms.assetid: 0be6ffc1-8afd-4d02-9a5d-e27dde05fde6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6a7d5bae07d3596902f94417cda20c3d40feed2f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="creating-a-windows-forms-toolbox-control"></a>Vytvoření ovládacího prvku Windows Forms sada nástrojů
Šablony položek ovládacího prvku Windows Forms sada nástrojů, která je součástí sady Visual Studio Extensibility Tools (VS SDK) umožňuje vytvoření ovládacího prvku, který je automaticky přidán do **sada nástrojů** při instalaci rozšíření. Toto téma ukazuje, jak používat šablony k vytvoření ovládacího prvku jednoduchý čítač, který distribuujete do jiných uživatelů.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-windows-forms-toolbox-control"></a>Vytvoření ovládacího prvku Windows Forms sada nástrojů  
 Šablona ovládacího prvku Windows Forms sady nástrojů vytvoří nedefinované uživatelského ovládacího prvku a poskytuje všechny funkce, které je povinné pro přidání do ovládacího prvku **sada nástrojů**.  
  
#### <a name="create-an-extension-with-a-windows-forms-toolbox-control"></a>Vytvoření rozšíření pomocí ovládacího prvku Windows Forms sada nástrojů  
  
1.  Vytvoření projektu VSIX s názvem `MyWinFormsControl`. Můžete najít v šabloně projektů VSIX **nový projekt** dialogové okno pod **Visual C# nebo rozšíření**.  
  
2.  Když se otevře projekt, přidejte **ovládacího prvku Windows Forms sady nástrojů** šablony položky s názvem `Counter`. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat / novou položku**. V **přidat novou položku** dialogové okno, přejděte na **Visual C# nebo rozšíření** a vyberte **ovládacího prvku Windows Forms sada nástrojů**  
  
3.  Tento postup přidá uživatelského ovládacího prvku `ProvideToolboxControlAttribute` <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute> umístit ovládacího prvku **sada nástrojů**a **Microsoft.VisualStudio.ToolboxControl** položku majetku v manifestu VSIX pro nasazení.  
  
### <a name="building-a-user-interface-for-the-control"></a>Vytváření uživatelské rozhraní pro ovládací prvek  
 `Counter` Ovládacího prvku vyžaduje dva podřízených ovládacích prvků: <xref:System.Windows.Forms.Label> zobrazíte aktuální počet a <xref:System.Windows.Forms.Button> obnovit počet na hodnotu 0. Žádné další podřízené ovládací prvky jsou požadované, protože hodnota čítače se zvýší prostřednictvím kódu programu volající.  
  
##### <a name="to-build-the-user-interface"></a>K vytvoření uživatelského rozhraní  
  
1.  V **Průzkumníku**, dvakrát klikněte na Counter.cs otevřít v návrháři.  
  
2.  Odeberte "Kliknutím sem!" **Tlačítko** které je zahrnuté ve výchozím nastavení při přidání šablony položky ovládacího prvku Windows Forms sady nástrojů.  
  
3.  Z **sada nástrojů**, přetáhněte `Label` ovládací prvek a potom `Button` řízení pod ním na plochu návrháře.  
  
4.  Změnit velikost celkového uživatelského ovládacího prvku do 150, 50 pixelů a změny velikosti tlačítko ovládacího prvku na 50, 20 pixelů.  
  
5.  V **vlastnosti** okno, nastavte následující hodnoty ovládacích prvků na návrhovou plochu.  
  
    |Ovládací prvek|Vlastnost|Hodnota|  
    |-------------|--------------|-----------|  
    |`Label1`|**Text**|""|  
    |`Button1`|**Jméno**|btnReset|  
    |`Button1`|**Text**|Resetování|  
  
### <a name="coding-the-user-control"></a>Kódování uživatelského ovládacího prvku  
 `Counter` Řízení zveřejní metoda se zvýší čítač událost má být aktivována vždy, když hodnota čítače se zvýší, `Reset` tlačítko a tři vlastnosti, které chcete uložit aktuální počet zobrazovaný text a jestli se má zobrazit nebo skrýt `Reset`tlačítko. `ProvideToolboxControl` Atribut určuje, kde v **sada nástrojů** `Counter` se zobrazí ovládací prvek.  
  
##### <a name="to-code-the-user-control"></a>Kód uživatelského ovládacího prvku  
  
1.  Dvakrát klikněte na formuláři otevřete její obslužnou rutinu události zatížení v okně kódu.  
  
2.  Výše metodu obslužné rutiny události ve třídě ovládacího prvku vytvořte celé k uložení hodnota čítače a řetězec k uložení zobrazovaný text, jak je znázorněno v následujícím příkladu.  
  
    ```csharp  
    int currentValue;  
    string displayText;  
    ```  
  
3.  Vytvořte následující deklarace veřejné vlastnosti.  
  
    ```csharp  
    public int Value {  
        get { return currentValue; }   
    }  
  
    public string Message {  
        get { return displayText; }  
        set { displayText = value; }  
    }  
  
    public bool ShowReset {  
        get { return btnReset.Visible; }  
        set { btnReset.Visible = value; }  
    }  
  
    ```  
  
     Volající mohou přistupovat tyto vlastnosti k získání a nastavení zobrazovaný text čítače a chcete zobrazit nebo skrýt `Reset` tlačítko. Volající můžete získat aktuální hodnota jen pro čtení `Value` vlastnost, ale nelze nastavit hodnotu přímo.  
  
4.  Vložte následující kód `Load` událostí pro ovládací prvek.  
  
    ```csharp  
    private void Counter_Load(object sender, EventArgs e)  
    {  
        currentValue = 0;  
        label1.Text = Message + Value;  
    }  
  
    ```  
  
     Nastavení **popisek** textu v <xref:System.Windows.Forms.UserControl.Load> událostí umožňuje načíst před použitím jejich hodnoty jsou vlastnosti cíle. Nastavení **popisek** text v konstruktoru by způsobilo prázdnou **popisek**.  
  
5.  Vytvořte následující metodu veřejné se zvýší čítače.  
  
    ```csharp  
    public void Increment()  
    {  
        currentValue++;  
        label1.Text = displayText + Value;  
        Incremented(this, EventArgs.Empty);  
    }  
  
    ```  
  
6.  Přidejte deklaraci pro `Incremented` událostí k třídě ovládacího prvku.  
  
    ```csharp  
    public event EventHandler Incremented;  
    ```  
  
     Volající můžete přidat obslužné rutiny k této události reagovat na změny v hodnotě čítače.  
  
7.  Vraťte se do návrhového zobrazení a dvakrát klikněte na `Reset` pro vygenerování `btnReset_Click` obslužné rutiny události a pak zadejte v, jak je znázorněno v následujícím příkladu.  
  
    ```csharp  
    private void btnReset_Click(object sender, EventArgs e)  
    {  
        currentValue = 0;  
        label1.Text = displayText + Value;  
    }  
  
    ```  
  
8.  Okamžitě výše definice třídy v `ProvideToolboxControl` atribut deklarace, změňte hodnotu z prvního parametru `"MyWinFormsControl.Counter"` k `"General"`. Toto nastaví název skupiny položek, který bude hostitelem ovládacího prvku **sada nástrojů**.  
  
     Následující příklad ukazuje `ProvideToolboxControl` atribut a definice upravenou třídy.  
  
    ```csharp  
    [ProvideToolboxControl("General", false)]  
    public partial class Counter : UserControl  
    ```  
  
### <a name="testing-the-control"></a>Testování ovládacího prvku  
 K testování **sada nástrojů** řídit, otestovat ji nejprve ve vývojovém prostředí a otestovat ji v kompilované aplikace.  
  
##### <a name="to-test-the-control"></a>Testování ovládacího prvku  
  
1.  Stiskněte klávesu F5.  
  
     Toto sestavení projektu a otevře druhou instanci experimentální sady Visual Studio, který má nainstalovaný ovládacího prvku.  
  
2.  V experimentální instanci sady Visual Studio, vytvoření **formulářové aplikace Windows** projektu.  
  
3.  V **Průzkumníku**, dvakrát klikněte na Form1.cs otevřít v návrháři, pokud ještě není otevřené.  
  
4.  V **sada nástrojů**, `Counter` řízení má být zobrazena v **Obecné** části.  
  
5.  Přetáhněte `Counter` řízení do svého formuláře a pak ho vyberte. `Value`, `Message`, A `ShowReset` vlastnosti se zobrazí v **vlastnosti** okno spolu s vlastnostmi, které se dědí z <xref:System.Windows.Forms.UserControl>.  
  
6.  Nastavte `Message` vlastnost `Count:`.  
  
7.  Přetáhněte <xref:System.Windows.Forms.Button> řízení formuláře a potom nastavit vlastnosti název a text na tlačítko `Test`.  
  
8.  Dvakrát klikněte na tlačítko Otevřít Form1.cs v zobrazení kódu a obslužná rutina kliknutí na vytvořit.  
  
9. V obslužné rutině klikněte na tlačítko volání `counter1.Increment()`.  
  
10. Ve funkci konstruktoru po zavolání `InitializeComponent`, typ `counter1``.``Incremented +=` a dvakrát stiskněte klávesu TAB.  
  
     Generuje úrovni formuláře obslužnou rutinu pro Visual Studio `counter1.Incremented` událostí.  
  
11. Zvýrazněte `Throw` příkaz v obslužné rutiny události, typ `mbox`, a potom stiskněte klávesu TAB dvakrát ke generování okno se zprávou z mbox fragment kódu.  
  
12. Na následujícím řádku, přidejte následující `if` / `else` blok k nastavit viditelnost `Reset` tlačítko.  
  
    ```csharp  
    if (counter1.Value < 5) counter1.ShowReset = false;  
    else counter1.ShowReset = true;  
    ```  
  
13. Stiskněte klávesu F5.  
  
     Otevře se formulář. `Counter` Ovládací prvek zobrazí následující text.  
  
     **Počet: 0**  
  
14. Klikněte na tlačítko **Test**.  
  
     Čítače se zvýší a Visual Studio zobrazí okno se zprávou.  
  
15. Zavřete okno se zprávou.  
  
     **Resetovat** tlačítko zmizí.  
  
16. Klikněte na tlačítko **Test** dokud nedosáhne čítač **5** zavření zprávy oknech pokaždé, když.  
  
     **Resetovat** tlačítko se znovu zobrazí.  
  
17. Klikněte na tlačítko **resetovat**.  
  
     Čítač obnoví na **0**.  
  
## <a name="next-steps"></a>Další kroky  
 Při vytváření **sada nástrojů** řízení, Visual Studio vytvoří soubor s názvem *ProjectName*VSIX ve složce \bin\debug\ projektu. Ovládací prvek můžete nasadit tím, že nahrajete soubor VSIX k síti nebo na webu. Když uživatel otevře soubor VSIX, je nainstalována a přidat do sady Visual Studio ovládacího prvku **sada nástrojů** na počítači uživatele. Alternativně můžete nahrát soubor VSIX [Galerie sady Visual Studio](http://go.microsoft.com/fwlink/?LinkID=123847) webové lokality tak, aby ji uživatelé mohli najít procházením v **nástroje nebo rozšíření a aktualizace** dialogové okno.  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření dalšími částmi sady Visual Studio](../extensibility/extending-other-parts-of-visual-studio.md)   
 [Vytvoření ovládacího prvku sady nástrojů WPF](../extensibility/creating-a-wpf-toolbox-control.md)   
 [Rozšíření dalšími částmi sady Visual Studio](../extensibility/extending-other-parts-of-visual-studio.md)   
 [Základní informace o vývoji ovládacích prvků Windows Forms](/dotnet/framework/winforms/controls/windows-forms-control-development-basics)