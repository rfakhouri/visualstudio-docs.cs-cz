---
title: "Pomocí místních souborů databáze v přehled řešení pro systém Office | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], data
- data [Office development in Visual Studio], local
- local data [Office development in Visual Studio]
ms.assetid: 7a920e6b-f0c3-4a62-b5dd-02668a6177b6
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 9d807c38af14249b265c411de31f6cde03855c60
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
  
  