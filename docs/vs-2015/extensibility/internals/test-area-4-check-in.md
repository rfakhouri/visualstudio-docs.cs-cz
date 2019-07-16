---
title: 'Testovací oblast 4: Vrátit se změnami | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], checking items in
- source control plug-ins, checking items in
ms.assetid: d0329fa8-7a8d-4d30-b67b-6f2a97b75a30
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 738b2608d5afa188cad38d92ed613307d2919ca0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68155959"
---
# <a name="test-area-4-check-in"></a>Testovací oblast 4: Vrácení se změnami
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Tento modul plug-in testu oblast správy zdrojového kódu obsahuje informace o odesílání aktualizované položky k úložišti verzí prostřednictvím **vrátit se změnami** příkazu.  
  
## <a name="command-menu-access"></a>Přístup do příkazu nabídky  
 Následující [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] integrované vývojové prostředí nabídky cesty se používají v testovacích procesech.  
  
##### <a name="check-in"></a>Přihlásit se:  
 **Soubor**, **správy zdrojového kódu**, **vrátit se změnami**.  
  
 **Soubor**, **vrátit se změnami**.  
  
 Místní nabídka **vrátit se změnami**.  
  
## <a name="common-expected-behavior"></a>Běžné očekávané chování  
  
- Projekty a soubory přidané do řešení nebo projekt pod správou zdrojového kódu se zobrazí v **vrátit se změnami** dialogové okno a **čekající vrácení se změnami** okna.  
  
- Po vrácení se změnami přidané položky se zobrazí ve správě zdrojového kódu.  
  
- Po vrácení se změnami jsou aktualizované položky správně označené verzí v úložišti.  
  
## <a name="test-cases"></a>Testovací případy  
 Tady jsou konkrétní testovací případy pro testovací oblast vrácení se změnami.  
  
### <a name="case-4a-modified-items"></a>Případu 4a: Změněné položky  
 Popisuje použití kontroly v akci aktualizovat soubor pod správou zdrojových kódů, která byla změněna.  
  
|Akce|Testovací kroky|Chcete-li ověřit očekávané výsledky|  
|------------|----------------|--------------------------------|  
|Upravte textový soubor, který byl rezervován, vrátit se změnami pouze soubor (**vrátit se změnami** dialogové okno)|1.  Vytvoření nového projektu pomocí textového souboru.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Přečtěte si a upravte textový soubor.<br />4.  Vrátit se změnami prostřednictvím dialogu vrátit se změnami (**souboru**, **správy zdrojových kódů**, **vrátit se změnami**).|Běžné očekávané chování.|  
|Upravte textový soubor, který byl rezervován, vrátit se změnami pouze soubor (**čekající vrácení se změnami** okna)|1.  Vytvoření nového projektu pomocí textového souboru.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Přečtěte si a upravte textový soubor.<br />4.  Vrátit se změnami prostřednictvím **čekající vrácení se změnami** okna.|Běžné očekávané chování.|  
  
### <a name="case-4b-adding-files"></a>Případu 4b: Přidávání souborů  
 Při přidání souboru do projektu nebo položky řešení, projekt nebo řešení musí také změnit. Proto nadřazený soubor je také rezervovat a musí být vráceny se změnami do dokončení přidání.  
  
|Akce|Testovací kroky|Chcete-li ověřit očekávané výsledky|  
|------------|----------------|--------------------------------|  
|Přidání textového souboru a vše se změnami (**vrátit se změnami** dialogové okno)|1.  Vytvořte nový projekt.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Přidání textového souboru do projektu.<br />4.  Prohlédněte si projekt přijměte, pokud se zobrazí výzva.<br />5.  Vyberte řešení v **Průzkumníka řešení**.<br />6.  Vrátit se změnami z **vrátit se změnami** dialogové okno.|Běžné očekávané chování.|  
|Přidání textového souboru a vše se změnami (**čekající vrácení se změnami** okna)|1.  Vytvořte nový projekt.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Přidání textového souboru do projektu.<br />4.  Prohlédněte si projekt přijměte, pokud se zobrazí výzva.<br />5.  Vrátit se změnami řešení z **čekající vrácení se změnami** okna.|Běžné očekávané chování|  
  
### <a name="case-4c-adding-projects"></a>Případ 4c: Přidávání projektů  
 Při přidání objektu project do řešení, musíte změnit taky řešení. Proto soubor řešení je také rezervovat a musí být vráceny se změnami do dokončení přidání.  
  
|Akce|Testovací kroky|Chcete-li ověřit očekávané výsledky|  
|------------|----------------|--------------------------------|  
|Přidat projekt do prázdné řešení pod správou zdrojových kódů (**vrátit se změnami** dialogové okno)|1.  Vytvořte prázdné řešení.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Přidáte nový projekt.<br />4.  Prohlédněte si řešení přijměte, pokud se zobrazí výzva.<br />5.  Vrátit se změnami z **vrátit se změnami** dialogové okno.|Běžné očekávané chování.|  
|Přidat projekt do prázdné řešení pod správou zdrojových kódů (**čekající vrácení se změnami** okna)|1.  Vytvořte prázdné řešení.<br />2.  Přidáte řešení do správy zdrojového kódu.<br />3.  Přidáte nový projekt.<br />4.  Prohlédněte si řešení přijměte, pokud se zobrazí výzva.<br />5.  Vrátit se změnami řešení z **čekající vrácení se změnami** okna.|Běžné očekávané chování.|  
  
## <a name="see-also"></a>Viz také  
 [Testovací příručka pro moduly plug-in správy zdrojového kódu](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)
