---
title: 'Postupy: Přidání a odebrání mapovaných složek | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Project.MappedFolder
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, mapped folders
- mapped folders [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 21ecf370134558d7b47faad1c215fa9a65019316
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56646210"
---
# <a name="how-to-add-and-remove-mapped-folders"></a>Postupy: Přidání a odebrání mapovaných složek
  Některé složky v Sharepointu, běžně používají, jako je Image a rozložení, jsou hluboko vložené hierarchie souborů. Mapování těchto složek do projektu služby SharePoint pro přístup k nim snadněji. Mapované složky jsou složky v projektu služby SharePoint, které odpovídají na fyzické umístění souborů v instalaci SharePoint serveru.

 Když nasadíte aplikaci služby SharePoint, obsah mapovaná složka a všechny její podsložky zkopírovány do řešení balíčku (.wsp) na server, na kterém běží SharePoint v zadaném umístění ve stromu složky Sharepointu. Toto umístění je určeno **umístění nasazení** vlastnost, která je nastavena pro mapovanou složku. Žádné podsložky ve složce pro mapovanou jsou vzhledem k **umístění nasazení** z namapované složky. Všimněte si, **umístění nasazení** nasazená položky určuje vlastnost, nikoli název mapované složky.
Mapované složky můžete přidat do projektu pomocí příkazů na panelu nabídek nebo místní nabídku pro projekt. Můžete použít **přidat SharePoint "Image" namapované složky** a **přidat SharePoint "Rozložení" složky** přidejte tyto namapované složky, které se používají nejčastěji. Můžete namapovat žádné další dostupné složky Sharepointu do svého projektu pomocí **přidat Sharepointové namapované složky** příkazu v místní nabídce a potom zadáte složky v **přidat namapované složky Sharepointu** dialogové okno.

## <a name="add-mapped-folders-to-a-project"></a>Do projektu přidat mapované složky
 Následující postup popisuje, jak přidat dvě mapované složky do projektu vizuální webové části. Pokud chcete začít, vytvoření projektu vizuální webové části.

#### <a name="to-add-mapped-folders-to-a-project"></a>Chcete-li přidat mapované složky do projektu

1.  V panelu nabídky zvolte **souboru** > **nový** > **projektu**.

2.  V **nový projekt** dialogového okna rozbalte buď **jazyka Visual Basic** nebo **Visual C#**  uzlu, rozbalte **Office/SharePoint** uzel a klikněte na tlačítko **řešení služby SharePoint** uzlu.

3.  V seznamu šablon projektu vyberte **Sharepointu 2013 vizuální webová část** šablony.

4.  V **název** zadejte **projekt testproject1 vyžaduje**a klikněte na tlačítko **OK** tlačítko.

5.  V **Průvodce přizpůsobením SharePoint**, zvolte **Dokončit** tlačítko Zachovat výchozí nastavení.

6.  V **Průzkumníka řešení**, zvolte uzel projektu a pak na panelu nabídek zvolte **projektu** > **přidat SharePoint "Image" namapované složky**.

     Složku s názvem **Imagí** se zobrazí ve vašem projektu a obsahuje podsložku s názvem projekt testproject1 vyžaduje. Tato mapovaná složka bude obsahovat bitových kopií pro projektu vizuální webové části.

7.  V **Průzkumníka řešení**, zvolte uzel projektu a pak na panelu nabídek zvolte **projektu** > **přidat Sharepointové namapované složky** zobrazíte  **Přidat složku služby SharePoint mapovat** dialogové okno.

8.  Ve stromovém zobrazení složek, které jsou k dispozici pro mapování, zvolte **prostředky** složky a klikněte na tlačítko **OK** tlačítko.

     Složku s názvem **prostředky** se zobrazí ve vašem projektu. Tato složka může ukládat položky, jako jsou soubory prostředků řetězce. Podsložky může být užitečné pro uspořádání obsahu z namapované složky, ale vytvoření automaticky při přidání mapovaná složka s použitím **přidat Sharepointové namapované složky** příkazu. Chcete-li přidat podsložky, zvolte **prostředky** složky a potom na panelu nabídek zvolte **projektu** > **novou složku**.

## <a name="change-the-deployment-location-of-a-mapped-folder"></a>Změna umístění nasazení z namapované složky
 Ve výchozím nastavení, mapované složky jsou přidány do konkrétního umístění vzhledem k Sharepointu kořenová cesta instalace, která token \<SharePointRoot > označuje. Ale toto umístění můžete změnit pomocí změny **umístění nasazení** vlastnost z namapované složky. Každý mapovaná složka má vlastní **umístění nasazení** vlastnost.

#### <a name="to-change-the-deployment-location-of-a-mapped-folder"></a>Chcete-li změnit umístění nasazení z namapované složky

1.  V projektu, který jste vytvořili dříve zvolte na mapovanou složku.

2.  V **vlastnosti** okno, zvolte tři tečky (![ASP.NET – Návrhář mobilních řešení Elipsa](../sharepoint/media/mwellipsis.gif "elipsa ASP.NET – Návrhář mobilních řešení")) tlačítko **nasazení umístění** vlastnost.

3.  V **přidat Sharepointové namapované složky** dialogové okno, přejděte do složky, do kterého chcete mapovanou složku tak, aby odkazoval.

4.  Vyberte uzel a klikněte na tlačítko **OK** tlačítko.

## <a name="rename-or-remove-mapped-folders"></a>Přejmenování a odebrání mapovaných složek

#### <a name="to-rename-or-remove-a-mapped-folder"></a>Přejmenování nebo odstranění mapované složky

1.  V projektu, který jste vytvořili dříve zvolte na mapovanou složku.

2.  Chcete-li přejmenovat mapovanou složku, otevřete místní nabídku, zvolte **přejmenovat**, zadejte nový název a stiskněte klávesu Enter.

     Jako alternativu můžete zvolit mapovaná složka, kterou chcete přejmenovat, otevřete **vlastnosti** okna a pak nastavte hodnotu **název složky** vlastnost na nový název.

3.  Pro mapovanou složku odeberte z projektu, otevřete místní nabídku, vyberte **odstranit**a klikněte na tlačítko **OK** tlačítko v dialogovém okně potvrďte odstranění.

## <a name="see-also"></a>Viz také:
- [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)
