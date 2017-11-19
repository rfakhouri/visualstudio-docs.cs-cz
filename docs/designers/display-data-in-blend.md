---
title: "Zobrazení dat v Blendu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87d31b6c-4607-4121-bb7d-cfc80390ab93
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1097a5724e1fcab96be99c58532e15fedd59da30
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="display-data-in-blend"></a>Zobrazení dat v Blendu
Můžete zobrazit ukázková data ve vašem Návrhář přizpůsobení rozložení stránek. Ukázková data můžete vygenerovat z nuly nebo pomocí existující třídy. Můžete také připojit k *dynamická data* který se zobrazí v aplikaci, když jej spustíte.  
  
 **V tomto tématu:**  
  
-   [Generovat ukázková data](#Scratch)  
  
-   [Generovat ukázková data z třídy](#Existing)  
  
-   [Zobrazit data za provozu v aplikaci WPF](#LiveWPF)  
  
-   [Zobrazit živé data v úložišti nebo telefonní aplikace](#LiveStore)  
  
##  <a name="Scratch"></a>Generovat ukázková data  
 Chcete-li vygenerovat ukázková data, otevřete dokumentu XAML. V **Data** panelu, vyberte **vytvoření ukázkových dat** ![](../designers/media/30540d76-7256-43ce-b5d9-4b2edf3d339f.png "30540d76-7256-43ce-b5d9-4b2edf3d339f") tlačítko a potom vyberte **nové ukázková Data**.  
  
 Definovat strukturu dat v **Data** panelu a pak vytvořte vazbu s prvky uživatelského rozhraní na libovolné stránce.  
  
 ![](../designers/media/496d7ebc-fe46-42f6-95a8-57b0e5be5d49.png "496d7ebc-fe46-42f6-95a8-57b0e5be5d49")  
  
 Pokud chcete, aby vaše ukázková data zobrazit na stránkách při spuštění aplikace, vyberte **zdroje dat možnosti** ![](../designers/media/ae1fd260-4f84-420d-b196-45fde357d81d.png "ae1fd260-4f84-420d-b196-45fde357d81d")a potom zvolte **povolit při spuštění aplikace**.  
  
 ![](../designers/media/05d5356d-91bb-4e6b-b3f7-29b76852c4b3.png "05d5356d-91bb-4e6b-b3f7-29b76852c4b3")  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [vytvoření ukázkových dat od začátku](http://www.bing.com/videos/search?q=blend%20data&qs=n&form=QBVR&pq=blend%20data&sc=8-7&sp=-1&sk=#view=detail&mid=F8F2449A76956D480FD2F8F2449A76956D480FD2).  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [kombinování si některé datová vazba s Blend](https://www.youtube.com/watch?v=LSwPB6CAvjg).  
  
##  <a name="Existing"></a>Generovat ukázková data z třídy  
 Pokud jste již vytvořili tříd, které popisují strukturu dat, můžete vygenerovat ukázková data z nich.  
  
 Pokud chcete vygenerovat ukázková data z třídy, otevřete dokument XAML a potom v **Data** panelu, klikněte na tlačítko **vytvoření ukázkových dat** ![](../designers/media/30540d76-7256-43ce-b5d9-4b2edf3d339f.png "30540d76-7256-43ce-b5d9-4b2edf3d339f") tlačítko a pak klikněte na tlačítko **vytvoření ukázkových dat z Třída**.  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [vytvoření ukázkových dat z třídy](http://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=video&cd=1&cad=rja&uact=8&ved=0CB0QtwIwAA&url=http%3A%2F%2Fchannel9.msdn.com%2FShows%2FInside%2BWindows%2BPhone%2FIWP54--Windows-Phone-Data-Binding-and-the-Magic-of-XAML&ei=F1oHVNryM4ysogSJ2oDYDw&usg=AFQjCNEYvw1WA1rdF7bfpj5RwMLUs7RCVg).  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [kombinování si některé datová vazba s Blend](https://www.youtube.com/watch?v=LSwPB6CAvjg).  
  
##  <a name="LiveWPF"></a>Zobrazit data za provozu v aplikaci WPF  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [vytvořit zdroj dat objektu](http://www.bing.com/videos/watch/video/using-an-objectdatasource-in-expression-blend/qmavx0xg).  
  
 **Podívejte se na krátké video:** ![nakonfigurovat nainstalované funkce](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [vytvořit zdroj dat XML](https://www.youtube.com/watch?v=RjQueappjqk&feature=youtube_gdata).  
  
##  <a name="LiveStore"></a>Zobrazit živé data v úložišti nebo telefonní aplikace  
 V tématu [funkční s daty a soubory (XAML)](http://msdn.microsoft.com/library/windows/apps/xaml/br229562.aspx).  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření uživatelského rozhraní pomocí nástroje Blend for Visual Studio](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)