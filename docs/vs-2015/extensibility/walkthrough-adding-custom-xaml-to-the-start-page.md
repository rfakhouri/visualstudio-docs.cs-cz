---
title: 'Návod: Přidání XAML vlastní úvodní stránku | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom start page
- xaml start page
ms.assetid: 9af4d5f9-1cfc-4221-aea7-c8cd3f7571a6
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 796beda7675d45698dd361e09f5b27e54d8b5da6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685055"
---
# <a name="walkthrough-adding-custom-xaml-to-the-start-page"></a>Návod: Přidání vlastního souboru XAML na úvodní stránku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [návod: Přidání vlastních XAML na úvodní stránku](https://docs.microsoft.com/visualstudio/extensibility/walkthrough-adding-custom-xaml-to-the-start-page).  
  
Tento návod ukazuje, jak vytvořit vlastní aplikaci Visual Studio úvodní stránky, která obsahuje webový prohlížeč.  
  
## <a name="adding-custom-xaml"></a>Přidání vlastní XAML  
  
1.  Vytvořit podle pokynů v úvodní stránka [vytvoření vlastní úvodní stránku](../extensibility/creating-a-custom-start-page.md).  
  
2.  V souboru MainWindow.xaml, vyhledejte \<mřížky > oddílu.  
  
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
  
## <a name="testing-the-custom-start-page"></a>Testování vlastní úvodní stránky  
  
1.  Stiskněte klávesu F5.  
  
     Otevře se experimentální instanci sady Visual Studio, s vlastní úvodní stránky nainstalované, ale nejsou vybrány.  
  
2.  V experimentální instanci sady Visual Studio, otevřete **Tools/Options / prostředí** stránky.  
  
3.  Vyberte **spuštění**. Na **přizpůsobit úvodní stránku** seznamu, vyberte soubor .xaml a klikněte na tlačítko **OK**.  
  
4.  Na **zobrazení** nabídky, klikněte na tlačítko **úvodní stránka**.  
  
5.  Klikněte na tlačítko **Bingu** kartu.  
  
     Měli byste vidět Bingu webové stránky.  
  
6.  Klikněte na tlačítko **MyButton** kartu.  
  
     Měli byste vidět **MyProject** tlačítko, které se otevře **nový projekt** dialogového okna.  
  
7.  Ukončete experimentální instanci.  
  
## <a name="applying-the-custom-start-page"></a>Použití vlastní úvodní stránky  
  
#### <a name="to-test-the-custom-start-page"></a>Chcete-li otestovat vlastní úvodní stránky  
  
1.  V **Nástroje / možnosti / prostředí**vyberte **spuštění**. Na **přizpůsobit úvodní stránku** seznamu, vyberte soubor .xaml a klikněte na tlačítko **OK**.  
  
## <a name="next-steps"></a>Další kroky  
 Visual Studio úvodní stránka nyní obsahuje kartu, která se zobrazí na kartě webového prohlížeče a MyButton kartu. Můžete vytvořit vlastní úvodní stránky, které mají další funkce pomocí *použití modelu code-behind* modelu Chcete-li přidat vlastní .dll, jak je znázorněno v [přidání uživatelského ovládacího prvku na úvodní stránku](../extensibility/adding-user-control-to-the-start-page.md). Vlastní úvodní stránky můžete sdílet s ostatními uživateli publikováním výsledný soubor .vsix [Galerie sady Visual Studio](http://go.microsoft.com/fwlink/?LinkID=123847) webový server nebo do jiného webu nebo síťové sdílené složky. Další informace najdete v tématu [nasazení vlastní úvodní stránky](../extensibility/deploying-custom-start-pages.md).  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení úvodní stránky](../ide/customizing-the-start-page-for-visual-studio.md)   
 [Kontejner ovládacích prvků WPF](http://msdn.microsoft.com/en-us/a0177167-d7db-4205-9607-8ae316952566)

