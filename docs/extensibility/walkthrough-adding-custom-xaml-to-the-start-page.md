---
title: "Návod: Přidání vlastních XAML pro úvodní stránku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom start page
- xaml start page
ms.assetid: 9af4d5f9-1cfc-4221-aea7-c8cd3f7571a6
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 924a6e2640002bc47eb75c903c46b5a170a9c308
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-adding-custom-xaml-to-the-start-page"></a>Návod: Přidání vlastních XAML pro úvodní stránku
Tento návod ukazuje, jak vytvořit vlastní Visual Studio – úvodní stránka obsahující webového prohlížeče.  
  
## <a name="adding-custom-xaml"></a>Přidání vlastní XAML  
  
1.  Vytvořit podle pokynů v úvodní stránka [vytváření vlastní – úvodní stránka](../extensibility/creating-a-custom-start-page.md).  
  
2.  V souboru MainWindow.xaml najít \<mřížky > části.  
  
3.  Přidat \<TabControl > elementu a \<TabItem > uvnitř \< mřížky > elementu, jak je znázorněno v následujícím příkladu.  
  
    ```xml  
    <Grid>  
        <TabControl>  
            <TabItem Header="Bing" Height="Auto">  
                <Frame Source="http://www.bing.com" />  
            </TabItem>  
        </TabControl>  
    </Grid>  
    ```  
  
4.  Přidejte druhý \<TabItem >, s \<tlačítko > elementu, které se otevře nový projekt:  
  
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
  
     Experimentální instanci sady Visual Studio otevře, s vlastní úvodní stránku nainstalován, ale není vybrán.  
  
2.  V experimentální instanci sady Visual Studio, otevřete **/Options nástroje / prostředí** stránky.  
  
3.  Vyberte **spuštění**. Na **přizpůsobení úvodní stránka** seznam, vyberte souboru XAML a klikněte na **OK**.  
  
4.  Na **zobrazení** nabídky, klikněte na tlačítko **– úvodní stránka**.  
  
5.  Klikněte **Bing** kartě.  
  
     Měli byste vidět na webové stránce služby Bing.  
  
6.  Klikněte **MyButton** kartě.  
  
     Měli byste vidět **MyProject** tlačítko, které se otevře **nový projekt** dialogové okno.  
  
7.  Ukončete experimentální instanci.  
  
## <a name="applying-the-custom-start-page"></a>Použití vlastní úvodní stránky  
  
#### <a name="to-test-the-custom-start-page"></a>K testování vlastní úvodní stránku  
  
1.  V **Nástroje / možnosti / prostředí**, vyberte **spuštění**. Na **přizpůsobení úvodní stránka** seznam, vyberte souboru XAML a klikněte na **OK**.  
  
## <a name="next-steps"></a>Další kroky  
 Visual Studio – úvodní stránka nyní obsahuje na kartě, který zobrazí kartu webového prohlížeče a na kartě MyButton. Můžete vytvořit vlastní spuštění stránky, které mají další funkce pomocí *kódu* modelu přidat vlastní .dll, jak je znázorněno v [přidání uživatelského ovládacího prvku na stránce Start](../extensibility/adding-user-control-to-the-start-page.md). Vlastní spuštění stránky můžete sdílet s ostatními uživateli tím, že publikujete výsledný soubor VSIX [Galerie sady Visual Studio](http://go.microsoft.com/fwlink/?LinkID=123847) webový server nebo na jiný webový server nebo síťové sdílené složky. Další informace najdete v tématu [nasazení vlastní spuštění stránky](../extensibility/deploying-custom-start-pages.md).  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení úvodní stránky](../ide/customizing-the-start-page-for-visual-studio.md)   
 [Ovládací prvky kontejneru WPF](http://msdn.microsoft.com/en-us/a0177167-d7db-4205-9607-8ae316952566)