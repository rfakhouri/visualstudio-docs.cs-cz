---
title: Vytvoření vlastní úvodní stránku | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d67e0c53-9f5a-45fb-a929-b9d2125c3c82
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
monikerRange: vs-2017
ms.openlocfilehash: 2b0b8c6fde31f4f4d9573381e511465e60086add
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66336668"
---
# <a name="creating-a-custom-start-page"></a>Vytvoření vlastní úvodní stránky

Můžete vytvořit vlastní úvodní stránky pomocí následujících kroků v tomto dokumentu.

## <a name="create-a-blank-start-page"></a>Vytvoření prázdné úvodní stránka

Nejprve se přesvědčte, tak, že vytvoříte prázdný úvodní stránka *.xaml* soubor, který má strukturu značku, která sadě Visual Studio rozpozná. Pak přidejte značky a modelu code-behind vzhled a funkce, které chcete vytvořit.

1. Vytvořte nový projekt typu **aplikace WPF** (**Visual C#**  > **Windows Desktop**).

2. Přidejte odkaz na `Microsoft.VisualStudio.Shell.14.0`.

3. Otevřete soubor XAML v editoru XML a změňte na nejvyšší úrovni \<okna > element \<UserControl > element bez odebrání všech deklarace oboru názvů.

4. Odeberte `x:Class` prohlášením element nejvyšší úrovně. Díky tomu obsah XAML kompatibilní s oknem nástroje Visual Studio, který je hostitelem úvodní stránky.

5. Přidejte následující deklarace oborů názvů na nejvyšší úrovni \<UserControl > element.

    ```vb
    xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.14.0"
    xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"
    ```

     Tyto obory názvů umožňují přístup k příkazy sady Visual Studio, ovládací prvky a nastavení uživatelského rozhraní. Další informace najdete v tématu [příkazy přidat sady Visual Studio na úvodní stránku](../extensibility/adding-visual-studio-commands-to-a-start-page.md).

     Následující příklad ukazuje značky *.xaml* soubor pro prázdné úvodní stránka. Všechny vlastní obsah by měly patřit do vnitřní <xref:System.Windows.Controls.Grid> elementu.

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

6. Přidání ovládacích prvků do prázdné \<UserControl > element tak, aby vyplnil ve vaší vlastní úvodní stránky. Informace o tom, jak přidat funkce, které jsou specifické pro Visual Studio najdete v tématu [příkazy přidat sady Visual Studio na úvodní stránku](../extensibility/adding-visual-studio-commands-to-a-start-page.md).

## <a name="test-and-apply-the-custom-start-page"></a>Testování a použít vlastní úvodní stránky

Nenastavujte primární instance sady Visual Studio spuštěné vlastní úvodní stránku, dokud můžete ověřit, že nehavaruje sady Visual Studio. Místo toho ji otestujte v experimentální instanci aplikace.

### <a name="to-test-a-manually-created-custom-start-page"></a>K testování ručně vytvořili vlastní úvodní stránky

1. Zkopírujte soubor XAML a všechny podpůrné textové soubory nebo značky soubory do *%USERPROFILE%\My Documents\Visual Studio 2015\StartPages\\*  složky.

2. Pokud úvodní stránky odkazuje na všechny ovládací prvky nebo typy v sestavení, které nejsou nainstalované Visual Studio, zkopírujte sestavení a vložte je do *{instalační složky sady Visual Studio} \Common7\IDE\PrivateAssemblies\\* .

3. Na příkazovém řádku aplikace Visual Studio, zadejte **devenv /rootsuffix Exp** otevřete experimentální instanci sady Visual Studio.

4. V experimentální instanci aplikace, přejděte **nástroje** > **možnosti** > **prostředí** > **spuštění** stránky a vyberte soubor XAML z **přizpůsobit úvodní stránku** rozevíracího seznamu.

5. Na **zobrazení** nabídky, klikněte na tlačítko **úvodní stránka**.

     Vlastní úvodní stránku má být zobrazena. Pokud chcete změnit všechny soubory, můžete musí Ukončete experimentální instanci, proveďte požadované změny, zkopírujte a vložte změněných souborů a znovu otevřete experimentální instanci a zobrazte změny.

### <a name="to-apply-the-custom-start-page-in-the-primary-instance-of-visual-studio"></a>Chcete-li použít vlastní úvodní stránku v primární instance sady Visual Studio

- Poté, co jste otestovali úvodní stránku a to přijde stabilní, použijte **přizpůsobit úvodní stránku** možnost **možnosti** dialogové okno vybrat jako úvodní stránku v primární instance sady Visual Studio

## <a name="see-also"></a>Viz také:

- [Návod: Přidat vlastní XAML na úvodní stránku](../extensibility/walkthrough-adding-custom-xaml-to-the-start-page.md)
- [Přidat uživatelský ovládací prvek na úvodní stránku](../extensibility/adding-user-control-to-the-start-page.md)
- [Přidání příkazů sady Visual Studio pro úvodní stránku](../extensibility/adding-visual-studio-commands-to-a-start-page.md)
- [Návod: Ukládat nastavení uživatele na úvodní stránce](../extensibility/walkthrough-saving-user-settings-on-a-start-page.md)
- [Nasazení vlastní úvodní stránky](../extensibility/deploying-custom-start-pages.md)