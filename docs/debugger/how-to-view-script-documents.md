---
title: 'Postupy: Zobrazení dokumentů skriptu | Dokumentace Microsoftu'
ms.date: 11/04/2016
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
ms.openlocfilehash: 3592056fdde7756f3fbe63d0dc5d86782fdf9a8b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53867722"
---
# <a name="how-to-view-script-documents"></a>Postupy: Zobrazení dokumentů skriptu
V dřívějších verzích [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], skript na straně klienta soubory vygenerované ze skriptu na straně serveru se zobrazily v okně Průzkumník skriptů. Okno Průzkumníka skriptu se často skrytý, aby dostupnosti skriptů na straně klienta nebyl vždy jasné.  
  
 V [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], skript na straně klienta soubory vygenerované ze skriptu na straně serveru se zobrazí v Průzkumníku řešení, který se zobrazí ve výchozím nastavení. V okně Průzkumník skriptů se odstranilo.  
  
 Soubory skriptu na straně klienta jsou viditelné pouze v případě, že jsou v režimu ladění nebo v režimu pozastavení. Zobrazí se v **dokumenty skriptu** uzlu.  
  
 Soubory skriptu na straně serveru jsou vždy viditelné. Zobrazí se v  **\<webu cesta >** uzlu. Název uzlu vypadá podobně jako v tomto příkladu: `c:\...\Website2\`  
  
### <a name="to-view-a-server-side-script-document"></a>Chcete-li zobrazit dokument skriptu na straně serveru  
  
1.  V **Průzkumníka řešení**, otevřete  **\<webu cesta >** uzlu.  
  
2.  Poklikejte na soubor skriptu, který chcete zobrazit.  
  
     Soubor skriptu na straně serveru se otevře v okně zdroje.  
  
### <a name="to-view-a-client-side-script-document"></a>Chcete-li zobrazit dokument skriptu na straně klienta  
  
1.  V **Průzkumníka řešení**, otevřete **dokumenty skriptu** uzlu.  
  
2.  Poklikejte na soubor skriptu, který chcete zobrazit.  
  
     Soubor skriptu na straně klienta se otevře v okně zdroje.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)