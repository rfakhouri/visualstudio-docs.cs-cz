---
title: 'Průvodce: Přidání XAML vlastní úvodní stránku | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- custom start page
- xaml start page
ms.assetid: 9af4d5f9-1cfc-4221-aea7-c8cd3f7571a6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
monikerRange: vs-2017
ms.openlocfilehash: 992937ea0c90e3734a38ba6f2e56b19918fd7375
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56709171"
---
# <a name="walkthrough-add-custom-xaml-to-the-start-page"></a>Průvodce: Přidat vlastní XAML na úvodní stránku

Tento návod ukazuje, jak vytvořit vlastní úvodní stránku sady Visual Studio, která obsahuje webový prohlížeč.

## <a name="add-custom-xaml"></a>Přidat vlastní XAML

1.  Vytvořit podle pokynů v úvodní stránku [vytvořit vlastní úvodní stránku](../extensibility/creating-a-custom-start-page.md).

2.  V *souboru MainWindow.xaml* souboru, vyhledejte \<mřížky > oddílu.

3.  Přidat \<TabControl > element a \<TabItem > uvnitř \< mřížky > element, jak je znázorněno v následujícím příkladu.

    ```xml
    <Grid>
        <TabControl>
            <TabItem Header="Bing" Height="Auto">
                <Frame Source="http://www.bing.com" />
            </TabItem>
        </TabControl>
    </Grid>
    ```

4.  Přidejte druhý \<TabItem >, pomocí \<tlačítko > element, který se otevře nový projekt:

    ```xml
    <Grid>
        <TabControl>
            <TabItem Header="MyButton" Height="Auto">
                <Button Name="btnNewProj" Content="New Project"
                    Command="{x:Static vscom:VSCommands.ExecuteCommand}"
                    CommandParameter="File.NewProject" >
                </Button>
            </TabItem>
            <TabItem Header="Bing" Height="Auto">
                <Frame Source="http://www.bing.com" />
            </TabItem>
        </TabControl>
    </Grid>
    ```

## <a name="test-the-custom-start-page"></a>Testování vlastní úvodní stránky

1.  Stisknutím klávesy **F5**.

     Otevře se experimentální instanci sady Visual Studio, s vlastní úvodní stránku nainstalované, ale nejsou vybrány.

2.  V experimentální instanci sady Visual Studio, otevřete **Tools/Options / prostředí** stránky.

3.  Vyberte **spuštění**. Na **přizpůsobit úvodní stránku** seznamu vyberte vaše *.xaml* souboru a klikněte na tlačítko **OK**.

4.  Na **zobrazení** nabídky, klikněte na tlačítko **úvodní stránka**.

5.  Klikněte na tlačítko **Bingu** kartu.

     Měli byste vidět Bingu webové stránky.

6.  Klikněte na tlačítko **MyButton** kartu.

     Měli byste vidět **MyProject** tlačítko, které se otevře **nový projekt** dialogového okna.

7.  Ukončete experimentální instanci.

Chcete-li použít vlastní úvodní stránky v **nástroje** > **možnosti** > **prostředí**vyberte **spuštění**. Na **přizpůsobit úvodní stránku** seznamu vyberte vaše *.xaml* souboru a klikněte na tlačítko **OK**.

## <a name="next-steps"></a>Další kroky

Úvodní stránku sady Visual Studio teď obsahuje kartu, která se zobrazí na kartě webového prohlížeče a MyButton kartu. Můžete vytvořit vlastní úvodní stránky, které mají další funkce pomocí *použití modelu code-behind* modelu Chcete-li přidat vlastní .dll, jak je znázorněno v [přidání uživatelského ovládacího prvku na úvodní stránku](../extensibility/adding-user-control-to-the-start-page.md). Vlastní úvodní stránky můžete sdílet s ostatními uživateli publikováním výsledný soubor .vsix [Galerie sady Visual Studio](http://go.microsoft.com/fwlink/?LinkID=123847) webový server nebo do jiného webu nebo síťové sdílené složky. Další informace najdete v tématu [nasazení vlastní úvodní stránky](../extensibility/deploying-custom-start-pages.md).

## <a name="see-also"></a>Viz také:

- [Přizpůsobení úvodní stránky](../ide/customizing-the-start-page-for-visual-studio.md)
- [Kontejner ovládacích prvků WPF](https://msdn.microsoft.com/library/a0177167-d7db-4205-9607-8ae316952566)