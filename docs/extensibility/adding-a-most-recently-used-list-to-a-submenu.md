---
title: "Přidání naposledy použité seznamu podnabídky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MRU lists
- menus, creating MRU list
- most recently used
ms.assetid: 27d4bbcf-99b1-498f-8b66-40002e3db0f8
caps.latest.revision: "46"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d622bd917548666e12eff6d29639f62d3ef4bc1f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="adding-a-most-recently-used-list-to-a-submenu"></a>Přidání většina nedávno používá seznamu podnabídky
Tento názorný postup je založený na ukázky v [přidání podnabídky do nabídky](../extensibility/adding-a-submenu-to-a-menu.md)a ukazuje, jak přidat do podnabídky dynamického seznamu. Dynamické seznamu je základem pro vytvoření seznamu naposledy (použitých).  
  
 Seznam dynamická nabídka začíná zástupný symbol v nabídce. Pokaždé, když se zobrazí v nabídce, integrované vývojové prostředí (IDE) sady Visual Studio VSPackage vyzve k zadání všechny příkazy, které se mají zobrazit v zástupného textu. Dynamického seznamu se mohou vyskytnout kdekoli v nabídce. Dynamické seznamy jsou však obvykle uložena a zobrazí samostatně na dílčích nebo na dolním okraji nabídky. Pomocí tyto vzory návrhu povolit dynamické seznam příkazů pro rozšíření a smlouvy bez ovlivnění pozici jinými příkazy v nabídce. V tomto návodu je dynamický seznam naposledy použitých zobrazí v dolní části existující podnabídky, oddělené od zbytku podnabídky pomocí linky.  
  
 Technicky je dynamický seznam použít také pro panel nástrojů. Ale jsme bránit toto využití, protože panelu nástrojů zůstanou beze změn, pokud uživatel provede konkrétní kroky pro ho změnit.  
  
 Tento návod vytvoří seznam naposledy použitých čtyři položek, které změnit jejich pořadí pokaždé, když je vybrán tento jeden z nich (vybrané položky se přesune do horní části seznamu).  
  
 Další informace o nabídky a .vsct souborů najdete v tématu [příkazy, nabídek a panelů nástrojů](../extensibility/internals/commands-menus-and-toolbars.md).  
  
## <a name="prerequisites"></a>Požadavky  
 Chcete-li provést tento postup, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="creating-an-extension"></a>Vytváření rozšíření  
  
-   Postupujte podle pokynů v [přidání podnabídky do nabídky](../extensibility/adding-a-submenu-to-a-menu.md) Vytvoření podnabídky, které se mění v následujících postupech.  
  
 Postupy v tomto návodu předpokládat, že je název VSPackage `TopLevelMenu`, což je název, který se používá v [přidání nabídky na panelu nabídek Visual Studio](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md).  
  
## <a name="creating-a-dynamic-item-list-command"></a>Vytváření příkazu pro dynamické položky seznamu  
  
1.  Otevřete TestCommandPackage.vsct.  
  
2.  V `Symbols` v části `GuidSymbol` uzel s názvem guidTestCommandPackageCmdSet, přidejte symbol pro `MRUListGroup` skupiny a `cmdidMRUList` příkaz následujícím způsobem.  
  
    ```csharp  
    <IDSymbol name="MRUListGroup" value="0x1200"/>  
    <IDSymbol name="cmdidMRUList" value="0x0200"/>  
    ```  
  
3.  V `Groups` část, přidejte skupinu deklarované po existující skupinu položek.  
  
    ```cpp  
    <Group guid="guidTestCommandPackageCmdSet" id="MRUListGroup"   
           priority="0x0100">  
        <Parent guid="guidTestCommandPackageCmdSet" id="SubMenu"/>  
    </Group>  
  
    ```  
  
4.  V `Buttons` část, uzel představují příkaz nově deklarované po existující položky tlačítko Přidat.  
  
    ```csharp  
    <Button guid="guidTestCommandPackageCmdSet" id="cmdidMRUList"  
        type="Button" priority="0x0100">  
        <Parent guid="guidTestCommandPackageCmdSet" id="MRUListGroup" />  
        <CommandFlag>DynamicItemStart</CommandFlag>  
        <Strings>  
            <CommandName>cmdidMRUList</CommandName>  
            <ButtonText>MRU Placeholder</ButtonText>  
                </Strings>  
    </Button>  
    ```  
  
     `DynamicItemStart` Příznak umožňuje příkaz, který má být generována dynamicky.  
  
5.  Sestavte projekt a spusťte ladění k testování zobrazení nový příkaz.  
  
     Na **TestMenu** nabídky, klikněte na tlačítko Nový dílčí **dílčí nabídky**, chcete-li zobrazit nový příkaz **zástupný symbol naposledy použitých**. Po implementace dynamických naposledy použitých seznam příkazů v dalším postupu tento příkaz Popisek budou nahrazeny tohoto seznamu pokaždé, když je otevřen podnabídky.  
  
## <a name="filling-the-mru-list"></a>Naplnění seznamu naposledy použitých  
  
1.  V TestCommandPackageGuids.cs, přidejte následující řádky po existující identifikátory příkazů v `TestCommandPackageGuids` definici třídy.  
  
    ```csharp  
    public const string guidTestCommandPackageCmdSet = "00000000-0000-0000-0000-00000000"; // get the GUID from the .vsct file  
    public const uint cmdidMRUList = 0x200;  
    ```  
  
2.  V TestCommand.cs přidejte následující příkaz using.  
  
    ```csharp  
    using System.Collections;  
    ```  
  
3.  Přidejte následující kód v konstruktoru TestCommand po posledním volání addcommand –. `InitMRUMenu` Budou později určené  
  
    ```csharp  
    this.InitMRUMenu(commandService);  
    ```  
  
4.  Přidejte následující kód ve třídě TestCommand. Tento kód inicializuje seznam řetězců, které představují položky k zobrazení v tomto seznamu.  
  
    ```csharp  
    private int numMRUItems = 4;  
    private int baseMRUID = (int)TestCommandPackageGuids.cmdidMRUList;  
    private ArrayList mruList;  
  
    private void InitializeMRUList()  
    {  
        if (null == this.mruList)  
        {  
            this.mruList = new ArrayList();  
            if (null != this.mruList)  
            {  
                for (int i = 0; i < this.numMRUItems; i++)  
                {  
                    this.mruList.Add(string.Format(CultureInfo.CurrentCulture,  
                        "Item {0}", i + 1));  
                }  
            }  
        }  
    }  
    ```  
  
5.  Po `InitializeMRUList` metoda, přidejte `InitMRUMenu` metoda. To inicializuje naposledy použitých seznam příkazů.  
  
    ```csharp  
    private void InitMRUMenu(OleMenuCommandService mcs)  
    {  
        InitializeMRUList();  
        for (int i = 0; i < this.numMRUItems; i++)  
        {  
            var cmdID = new CommandID(  
                new Guid(TestCommandPackageGuids.guidTestCommandPackageCmdSet), this.baseMRUID + i);  
            var mc = new OleMenuCommand(  
                new EventHandler(OnMRUExec), cmdID);  
            mc.BeforeQueryStatus += new EventHandler(OnMRUQueryStatus);  
            mcs.AddCommand(mc);  
        }  
    }  
    ```  
  
     Musíte vytvořit objekt příkazu nabídky pro každou položku možná v tomto seznamu. Volání IDE `OnMRUQueryStatus` metoda pro každou položku v seznamu naposledy použitých, dokud nejsou žádné další položky. Ve spravovaném kódu je jediný způsob, jakým IDE vědět, že neexistují žádné další položky, nejprve vytvořte všechny položky možné. Pokud chcete, můžete označit další položky, jako nejsou viditelné v první pomocí `mc.Visible = false;` po vytvoření příkazu nabídky. Tyto položky lze poté zviditelnit později pomocí `mc.Visible = true;` v `OnMRUQueryStatus` metoda.  
  
6.  Po `InitMRUMenu` metoda, přidejte následující `OnMRUQueryStatus` metoda. Toto je obslužná rutina, která nastaví text, pro každou položku naposledy použitých.  
  
    ```csharp  
    private void OnMRUQueryStatus(object sender, EventArgs e)  
    {  
        OleMenuCommand menuCommand = sender as OleMenuCommand;  
        if (null != menuCommand)  
        {  
            int MRUItemIndex = menuCommand.CommandID.ID - this.baseMRUID;  
            if (MRUItemIndex >= 0 && MRUItemIndex < this.mruList.Count)  
            {  
                menuCommand.Text = this.mruList[MRUItemIndex] as string;  
            }  
        }  
    }  
    ```  
  
7.  Po `OnMRUQueryStatus` metoda, přidejte následující `OnMRUExec` metoda. Toto je obslužná rutina pro výběr naposledy použitých položky. Tato metoda Přesune vybranou položku do horní části seznamu a potom zobrazí vybranou položku v okně se zprávou.  
  
    ```csharp  
    private void OnMRUExec(object sender, EventArgs e)  
    {  
        var menuCommand = sender as OleMenuCommand;  
        if (null != menuCommand)  
        {  
            int MRUItemIndex = menuCommand.CommandID.ID - this.baseMRUID;  
            if (MRUItemIndex >= 0 && MRUItemIndex < this.mruList.Count)  
            {  
                string selection = this.mruList[MRUItemIndex] as string;  
                for (int i = MRUItemIndex; i > 0; i--)  
                {  
                    this.mruList[i] = this.mruList[i - 1];  
                }  
                this.mruList[0] = selection;  
                System.Windows.Forms.MessageBox.Show(  
                    string.Format(CultureInfo.CurrentCulture,  
                                  "Selected {0}", selection));  
            }  
        }  
    }  
  
    ```  
  
## <a name="testing-the-mru-list"></a>Testování seznamu naposledy použitých  
  
#### <a name="to-test-the-mru-menu-list"></a>K testování seznamu v nabídce naposledy použitých  
  
1.  Sestavte projekt a spusťte ladění  
  
2.  Na **TestMenu** nabídky, klikněte na tlačítko **vyvolání TestCommand**. Tato funkce zobrazí okno se zprávou, která určuje, že byl vybrán příkaz.  
  
    > [!NOTE]
    >  Tento krok je nutný k vynucení VSPackage načtení a správně zobrazuje seznam naposledy použitých. Pokud tento krok přeskočíte, seznam naposledy použitých se nezobrazí.  
  
3.  Na **testovací nabídky** nabídky, klikněte na tlačítko **dílčí nabídky**. Čtyři položek seznamu se zobrazí na konci podnabídky níže oddělovač. Když kliknete na tlačítko **3 položky**, okno se zprávou by měla zobrazit a zobrazit text "Vybrané položky 3". (Pokud seznam čtyři položky nezobrazí, zkontrolujte, jestli jste postupovali podle pokynů v předchozím kroku.)  
  
4.  Znovu otevřete podnabídky. Všimněte si, že **3 položky** je nyní v horní části seznamu a dalších položek se nabídne o jednu pozici dolů. Klikněte na tlačítko **3 položky** znovu a Všimněte si, okno se zprávou stále zobrazuje "Vybrané položky 3", označující, že se text správně přesunul do nového umístění společně s příkaz popisek.  
  
## <a name="see-also"></a>Viz také  
 [Dynamicky přidání položek nabídky](../extensibility/dynamically-adding-menu-items.md)