---
title: 'Postupy: zobrazení dokumentů skriptu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Script Explorer
ms.assetid: 8b621e53-4508-4b4a-9995-70995b0b9ac8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 62c62212e72561817b58cf1496fff20a05745277
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-view-script-documents"></a>Postupy: Zobrazení dokumentů skriptu
V dřívějších verzích [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], klientský skript soubory vytvořené ze skriptu server na straně zobrazovaly v okně Průzkumníka skriptu. Okno Průzkumníka skriptu se často skrytá, tak, aby nebyla dostupnost klientský skript vždy zřejmé.  
  
 V [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], klientský skript soubory generované ze skriptu na straně serveru se zobrazí v Průzkumníku řešení, který se zobrazí ve výchozím nastavení. Okno Průzkumníka skriptu byly odstraněny.  
  
 Soubory skriptu na straně klienta jsou viditelná jenom v případě, že jste v režimu ladění nebo v režimu pozastavení. Se objeví v **dokumentů skriptu** uzlu.  
  
 Soubory skriptu na straně serveru jsou vždy viditelné. Se objeví v  **\<webu Pathname >** uzlu. Název uzlu vypadá takto: v tomto příkladu: `c:\...\Website2\`  
  
### <a name="to-view-a-server-side-script-document"></a>Chcete-li zobrazit dokumentu skript na straně serveru  
  
1.  V **Průzkumníku řešení**, otevřete  **\<webu Pathname >** uzlu.  
  
2.  Poklikejte na soubor skriptu, který chcete zobrazit.  
  
     Skripty na straně serveru soubor se otevře v okně zdroje.  
  
### <a name="to-view-a-client-side-script-document"></a>Chcete-li zobrazit skript na straně klienta dokument  
  
1.  V **Průzkumníku řešení**, otevřete **dokumentů skriptu** uzlu.  
  
2.  Poklikejte na soubor skriptu, který chcete zobrazit.  
  
     Soubor skriptu na straně klienta se otevře v okně zdroje.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)