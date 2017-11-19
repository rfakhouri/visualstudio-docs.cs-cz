---
title: "Vytváření vlastní úvodní stránku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d67e0c53-9f5a-45fb-a929-b9d2125c3c82
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d9782e51688ae1ef4fda3ed52636de54149fa79e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="creating-a-custom-start-page"></a>Vytváření vlastní úvodní stránky
Můžete vytvořit vlastní úvodní stránku podle kroků v tomto dokumentu.  
  
## <a name="creating-a-blank-start-page"></a>Vytvoření prázdné úvodní stránky  
 Nejprve zkontrolujte prázdná stránka Start vytvořením souboru XAML, který má strukturu značku, která pozná, Visual Studio. Potom na značek a kódu k vytvoření vzhled a funkce, které chcete přidáte.  
  
#### <a name="to-create-a-blank-start-page"></a>Chcete-li vytvořit prázdná stránka Start  
  
1.  Vytvořte nový projekt typu **aplikaci WPF** (**Visual C# / Windows Desktop**.  
  
2.  Přidat odkaz na `Microsoft.VisualStudio.Shell.14.0`.  
  
3.  Otevřete soubor XAML v editoru XML a změňte nejvyšší úrovně \<okno > elementu, který chcete \<UserControl > elementu bez odebrat všechny deklarace oboru názvů.  
  
4.  Odeberte `x:Class` deklaraci ze element nejvyšší úrovně. Součástí obsahu XAML díky kompatibilní s okno nástroje Visual Studio, který je hostitelem úvodní stránky.  
  
5.  Přidejte následující deklarace oborů názvů nejvyšší úrovně \<UserControl > elementu.  
  
    ```  
    xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.14.0"  
    xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"  
    ```  
  
     Tyto obory názvů umožňují přístup příkazy sady Visual Studio, ovládací prvky a nastavení uživatelského rozhraní. Další informace najdete v tématu [přidání příkazy sady Visual Studio pro úvodní stránku](../extensibility/adding-visual-studio-commands-to-a-start-page.md).  
  
     Následující příklad ukazuje kód v souboru XAML pro prázdné stránky Start. Všechny vlastní obsah by měl přejděte v vnitřní <xref:System.Windows.Controls.Grid> elementu.  
  
    ```vb  
    <UserControl  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
        xmlns:MyNamespace="clr-namespace:ManualStartPage;assembly=ManualStartPage"  
        xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.14.0"  
                xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"  
        xmlns:local="clr-namespace:StartPageHost"  
        mc:Ignorable="d"  
         Height="350" Width="525">  
        <Grid>  
        <!--Add content here.-->  
        </Grid>  
    </UserControl>  
    ```  
  
6.  Přidání ovládacích prvků do prázdné \<UserControl > element vyplnit vaše vlastní stránky Start. Informace o tom, jak přidat funkce, které jsou specifické pro Visual Studio najdete v tématu [přidání příkazy sady Visual Studio pro úvodní stránku](../extensibility/adding-visual-studio-commands-to-a-start-page.md).  
  
## <a name="testing-and-applying-the-custom-start-page"></a>Testování a použití vlastní úvodní stránku  
 Nenastavujte primární instance sady Visual Studio spouštět vlastní úvodní stránku až ověříte, že není chybu sady Visual Studio. Místo toho testování v experimentální instanci.  
  
#### <a name="to-test-a-manually-created-custom-start-page"></a>K testování ručně vytvořené vlastní stránky Start  
  
1.  Kopírování souboru XAML a všechny podpůrné textových souborů nebo značek souborů do **%USERPROFILE%\My Documents\Visual Studio 2015\StartPages\\**  složky.  
  
2.  Pokud všechny ovládací prvky nebo typy v sestavení, které nejsou nainstalované Visual Studio, odkazuje na úvodní stránky, zkopírujte sestavení a vložte je do *instalační složka nástroje Visual Studio***\Common7\IDE\ PrivateAssemblies\\**.  
  
3.  Na příkazovém řádku Visual Studio, zadejte **devenv /rootsuffix Exp** otevřete experimentální instanci sady Visual Studio.  
  
4.  V experimentální instance, přejděte do **Nástroje / možnosti / prostředí nebo spuštění** a vyberte souboru XAML z **přizpůsobení úvodní stránka** rozevíracího seznamu.  
  
5.  Na **zobrazení** nabídky, klikněte na tlačítko **– úvodní stránka**.  
  
     Má být zobrazena vlastní úvodní stránky. Pokud chcete změnit všechny soubory, musíte Ukončete experimentální instanci, proveďte požadované změny, zkopírovat a vložit změněné soubory a pak znovu otevřete experimentální instanci Chcete-li zobrazit změny.  
  
#### <a name="to-apply-the-custom-start-page-in-the-primary-instance-of-visual-studio"></a>Chcete-li použít vlastní úvodní stránku v primární instance sady Visual Studio  
  
-   Po testování úvodní stránku a zjistila, že se stabilní, použijte **přizpůsobení úvodní stránka** možnost **možnosti** dialogové okno vybrat jako úvodní stránku v primární instance sady Visual Studio  
  
## <a name="see-also"></a>Viz také  
 [Návod: Přidání vlastních XAML pro úvodní stránku](../extensibility/walkthrough-adding-custom-xaml-to-the-start-page.md)   
 [Přidání uživatelského ovládacího prvku do úvodní stránky](../extensibility/adding-user-control-to-the-start-page.md)   
 [Přidání příkazů sady Visual Studio na úvodní stránky](../extensibility/adding-visual-studio-commands-to-a-start-page.md)   
 [Návod: Ukládání uživatelských nastavení na stránce Start](../extensibility/walkthrough-saving-user-settings-on-a-start-page.md)   
 [Nasazení vlastní úvodní stránky](../extensibility/deploying-custom-start-pages.md)