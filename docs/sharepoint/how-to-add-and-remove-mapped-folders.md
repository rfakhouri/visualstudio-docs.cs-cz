---
title: "Postupy: Přidání a odebrání mapovaných složek | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.Project.MappedFolder
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, mapped folders
- mapped folders [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 29809344ee8a3f446589ba84f2fc47b1cf407582
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-and-remove-mapped-folders"></a>Postupy: Přidání a odebrání mapovaných složek
  Některé nejčastěji používané složky ve službě SharePoint, například bitové kopie a rozložení, jsou hluboko vložené v hierarchii souborů. Tyto složky můžete mapovat do projektu služby SharePoint na snadněji používat. Mapované složky jsou složky v projektu služby SharePoint, které odpovídají na fyzické umístění souborů v instalaci serveru SharePoint.  
  
 Když nasadíte aplikaci služby SharePoint, obsah mapované složky a všech jejích podsložkách se zkopírují balíček řešení (WSP) na server se systémem SharePoint do zadaného umístění ve stromové struktuře složek služby SharePoint. Toto umístění je dáno **umístění nasazení** vlastnost, která je nastavena pro mapované složky. Všechny podsložky ve složce namapované jsou vzhledem k **umístění nasazení** mapované složky. Všimněte si, že **umístění nasazení** vlastnost není název mapované složky Určuje, kde jsou nasazeny položky.  
  
 Mapované složky můžete přidat do projektu pomocí příkazů v panelu nabídek nebo místní nabídku pro projekt. Můžete použít **složky namapované "Bitových kopií" Přidat SharePoint** a **přidat SharePoint "Rozložení" složky** příkazy přidat ty namapované složky, které se nejčastěji používají. Můžete namapovat žádné další dostupné složky služby SharePoint do projektu s použitím **přidat složku SharePoint mapovat** příkaz v místní nabídce a potom zadáte složky v **přidat SharePoint mapovat složku** dialogové okno.  
  
## <a name="adding-mapped-folders-to-a-project"></a>Přidávání mapované složky do projektu  
 Následující postup popisuje, jak přidat dva mapované složky na projekt visual webové části. Pokud chcete spustit, vytvoříte projekt visual část.  
  
#### <a name="to-add-mapped-folders-to-a-project"></a>Mapované složky přidat do projektu  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
2.  V **nový projekt** dialogové okno, rozbalte seznam buď **jazyka Visual Basic** nebo **Visual C#** uzlu, rozbalte **Office nebo SharePoint** uzlu a potom Vyberte **řešení služby SharePoint** uzlu.  
  
3.  V seznamu šablon projektu, vyberte **webové části služby SharePoint 2013 Visual** šablony.  
  
4.  V **název** zadejte **TestProject1**a potom zvolte **OK** tlačítko.  
  
5.  V **Průvodce vlastním nastavením SharePoint**, vyberte **Dokončit** tlačítko ponechejte výchozí nastavení.  
  
6.  V **Průzkumníku řešení**, vyberte uzel projektu a potom na řádku nabídek zvolte **projektu**, **složky namapované "Bitových kopií" Přidat SharePoint**.  
  
     Složku s názvem **bitové kopie** se zobrazí ve vašem projektu a obsahuje podsložku s názvem TestProject1. Tato složka namapované bude obsahovat bitové kopie pro součást visual webový projekt.  
  
7.  V **Průzkumníku řešení**, vyberte uzel projektu a potom na řádku nabídek zvolte **projektu**, **přidat složku SharePoint mapovat** zobrazíte **přidat SharePoint mapovat složky** dialogové okno.  
  
8.  Ve stromovém zobrazení složek, které jsou k dispozici pro mapování, zvolte **prostředky** složku a potom zvolte **OK** tlačítko.  
  
     Složku s názvem **prostředky** se zobrazí ve vašem projektu. Tato složka může ukládat položek, jako jsou soubory prostředků řetězec. Podsložky může být užitečná pro uspořádání obsahu mapované složky, ale vytváří automaticky při přidání mapované složky pomocí **přidat složku SharePoint mapovat** příkaz. Při přidávání podsložku, vyberte **prostředky** složku a potom na řádku nabídek zvolte **projektu**, **novou složku**.  
  
## <a name="changing-the-deployment-location-of-a-mapped-folder"></a>Změna umístění nasazení mapované složky  
 Ve výchozím nastavení jsou mapované složky přidán do konkrétní umístění relativní k cestě instalace kořenové služby SharePoint, který označuje token {SharePointRoot}. Toto umístění však můžete změnit změnou **umístění nasazení** vlastnost mapované složky. Každý mapované složky má svou vlastní **umístění nasazení** vlastnost.  
  
#### <a name="to-change-the-deployment-location-of-a-mapped-folder"></a>Chcete-li změnit umístění nasazení mapované složky  
  
1.  V projektu, který jste vytvořili dříve zvolte mapované složky.  
  
2.  V **vlastnosti** okně zvolte se třemi tečkami (![ASP.NET – Návrhář mobilních řešení elipsy](../sharepoint/media/mwellipsis.gif "ASP.NET – Návrhář mobilních řešení elipsy")) na tlačítko **nasazení umístění** vlastnost.  
  
3.  V **přidat složku SharePoint mapovat** dialogové okno, přejděte do složky, do kterého chcete mapované složky tak, aby odkazoval.  
  
4.  Vyberte uzel a potom vyberte **OK** tlačítko.  
  
## <a name="renaming-or-removing-mapped-folders"></a>Přejmenování nebo odstranění mapované složky  
  
#### <a name="to-rename-or-remove-a-mapped-folder"></a>Přejmenovat nebo odebrat mapované složky  
  
1.  V projektu, který jste vytvořili dříve zvolte mapované složky.  
  
2.  Pokud chcete přejmenovat mapované složky, otevřete jeho místní nabídky, zvolte **přejmenovat**, zadejte nový název a potom vyberte klávesu Enter.  
  
     Jako alternativu můžete mapované složky, kterou chcete přejmenovat, otevřete **vlastnosti** okno a pak nastavte hodnotu **název složky** vlastnost na nový název.  
  
3.  Mapované složky odebrat z projektu, otevřete jeho místní nabídky, zvolte **odstranit**a potom zvolte **OK** tlačítka v dialogovém okně potvrďte odstranění.  
  
## <a name="see-also"></a>Viz také  
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
  