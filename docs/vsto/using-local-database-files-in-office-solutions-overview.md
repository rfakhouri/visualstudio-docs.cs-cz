---
title: Pomocí místních souborů databáze v přehled řešení pro systém Office | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], data
- data [Office development in Visual Studio], local
- local data [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a171fe12a1476e19c46f0aef704342de375c7865
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="using-local-database-files-in-office-solutions-overview"></a>Přehled použití místních souborů databáze v řešeních pro systém Office
  Ve vašem řešení Office můžete zahrnout soubor databáze, jako je například SQL Server Express (MDF) soubor nebo soubor aplikace Microsoft Office Access (.mdb). To umožňuje koncovým uživatelům udržovat místní databázi v situacích, kdy není povinné, například v místní inventáře řešení, které se používá v jednom počítači zachování do centralizované databáze.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="importing-the-database-file-into-a-project"></a>Importování souboru databáze do projektu  
 Chcete-li importovat soubor databáze do projektu, použijte **Průvodce konfigurací zdroje dat** vytvořit zdroj dat na základě souboru databáze. Průvodce přidá do projektu soubor databáze a typové datové sady.  
  
## <a name="deploying-the-database-file"></a>Nasazení souboru databáze  
 **Průvodce konfigurací zdroje dat** používá relativní cesta k vytvoření připojení k souboru místní databáze. To umožňuje kopírovat řešení z jednoho počítače do jiného, pokud chcete zachovat relativní umístění souborů.  
  
 Pokud nasadit řešení na server a pak distribuovat dokument pro každý koncového uživatele, musíte taky ručně distribuovat soubor databáze a nainstalujte ho do stejné pozici relativně k dokumentu. To znamená, že koncový uživatel nemůže přesunout dokumentu nového umístění na svém počítači, pokud uživatel také přesune soubor databáze.  
  
## <a name="local-database-files-and-caching-the-dataset"></a>Místní databázové soubory a ukládání do mezipaměti datové sady  
 V řešení na úrovni dokumentu pro aplikaci Microsoft Office Excel a Microsoft Office Word, můžete mezipaměti datové sady v dokumentu označením instance datovou sadu s atributem <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute>. Když přidáte databázový soubor do projektu s použitím **Průvodce konfigurací zdroje dat**, typové datové sady se automaticky přidá do projektu. Je občas nutné použít <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> pro tuto datovou sadu, protože data jsou místní na počítači uživatele. Další informace najdete v tématu [ukládání dat do mezipaměti](../vsto/caching-data.md).  
  
## <a name="see-also"></a>Viz také  
 [Vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Postupy: naplnění dokumentů daty z databáze](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [Postupy: aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Ukládaní dat do mezipaměti](../vsto/caching-data.md)  
  
  