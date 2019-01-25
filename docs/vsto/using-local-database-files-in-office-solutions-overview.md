---
title: Použití místních souborů databáze v přehled řešení pro systém Office
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], data
- data [Office development in Visual Studio], local
- local data [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: eec0a2adcb462bd2bb169cb997ce2fe352b0c72a
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54872700"
---
# <a name="use-local-database-files-in-office-solutions-overview"></a>Použití místních souborů databáze v přehled řešení pro systém Office
  Můžete zahrnout soubor databáze, jako je například SQL Server Express (*.mdf*) souboru nebo Microsoft Office Access (*.mdb*) soubor, ve vašem řešení Office. To umožňuje koncovým uživatelům udržovat místní databázi v situacích, kde není povinné, například v řešení místní inventář, který se používá v jednom počítači zachování do centralizované databáze.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="import-the-database-file-into-a-project"></a>Importovat soubor databáze do projektu  
 Chcete-li importovat soubor databáze do projektu, použijte **Průvodce konfigurací zdroje dat** vytvořit zdroj dat na základě souboru databáze. Průvodce přidá do projektu soubor databáze a typové datové sady.  
  
## <a name="deploy-the-database-file"></a>Nasazení souboru databáze  
 **Průvodce konfigurací zdroje dat** používá relativní cestu k vytvoření připojení k souboru místní databáze. To umožňuje kopírovat řešení z jednoho počítače do jiného, pokud je udržovat relativní umístění souborů.  
  
 Pokud vaše řešení nasadit na server a pak distribuovat dokument pro každý koncový uživatel musí také ručně distribuovat databázový soubor a nainstalujte ji na stejné pozici vzhledem k dokumentu. To znamená, koncovému uživateli nelze přesunout dokument do nového umístění svého počítače, pokud také přesune soubor databáze.  
  
## <a name="local-database-files-and-caching-the-dataset"></a>Místních souborů databáze a ukládání do mezipaměti datovou sadu  
 V řešeních na úrovni dokumentu pro aplikaci Microsoft Office Excel a Microsoft Office Word, můžete ukládat do mezipaměti datových sad v dokumentu instance datové sady s atributem označením <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute>. Když přidáte databázový soubor do projektu s použitím **Průvodce konfigurací zdroje dat**, typové datové sady je automaticky přidán do projektu. Je zřídka nezbytné použít <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> pro tuto datovou sadu, protože data jsou již místní na počítači uživatele. Další informace najdete v tématu [ukládat data do mezipaměti](../vsto/caching-data.md).  
  
## <a name="see-also"></a>Viz také:  
 [Vytvoření vazby dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Postupy: Naplnění dokumentů daty z databáze](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [Postupy: Aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Data v mezipaměti](../vsto/caching-data.md)  
