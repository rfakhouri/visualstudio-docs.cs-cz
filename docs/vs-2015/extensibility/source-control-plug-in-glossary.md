---
title: Glosář modulu Plug-in ovládací prvek zdroje | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- glossary [Visual Studio SDK]
- source control plug-ins, glossary
ms.assetid: f224bbc9-38fc-4c80-ab09-51dcc8969f8e
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f5120a5c6678cac32ef65e08ef7dc34649364cf9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68160609"
---
# <a name="source-control-plug-in-glossary"></a>Glosář modulu plug-in zdrojového kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Užitečné následující pojmy a definice se vztahují k dokumentaci zdrojového ovládacího prvku modulu Plug-in SDK.  
  
## <a name="definitions"></a>Definice  
 Vrácení se změnami  
 Když uživatel provede změny do funkční kopie, musí uživatel odeslat změny z pracovní kopie do úložiště správy centrální zdrojového kódu. Tím se vytvoří nová revize souboru, který je k dispozici jiným uživatelům. Tento proces se nazývá vrácení se změnami.  
  
 Rezervovat  
 V rámci žádosti o pracovní kopie v úložišti informuje úložiště vaším záměrem jej upravit. Pracovní kopie odráží stav projektu od okamžiku, kdy je rezervován.  
  
 Klient  
 Program, který využívá systém správy zdrojového kódu. Pro účely této dokumentace je integrované vývojové prostředí sady Visual Studio.  
  
 Komentář  
 Zpráva popisující změny, které uživatel může připojit k revizi při provádění operaci správy zdrojových kódů.  
  
 Konflikt  
 Situace, když dva uživatelé pokusí vrátit se změnami do stejné oblasti stejného souboru. Obvykle musí být provedeno sloučení.  
  
 Adresář  
 Místní složky na straně klienta se označuje jako adresář. Toto je kopírování, ve kterém uživatel ve skutečnosti provádí změny. Může být mnoho pracovních kopií daného projektu. obecně každý vývojář má svůj vlastní kopie.  
  
 získat  
 Operace get přináší uživatele pracovní kopie aktuální kopii úložiště. Na rozdíl od checkout get provést, pokud se uživatel jednoduše potřebuje nejnovější ale si klade za cíl neprovádějte žádné změny.  
  
 Historie  
 Obvykle je souhrn všech rezervace, vrácení se změnami, aktualizace, značky a verzí v úložišti správy zdrojů.  
  
 IDE – integrované vývojové prostředí  
 Obvykle odkazuje na Visual Studio integrované vývojové prostředí. Ale může také odkazovat na jiné prostředí klienta, které rozhraní API modulu Plug-in zdroje ovládacího prvku.  
  
 Sloučit  
 Proces, během kterého nejmíň dva zdroje jsou soubory kódu se spojí dohromady a tvoří nový soubor, který zahrnuje všechny funkce z předchozí soubory. Tento koncept je důležité ve správě verzí místo, kde dva nebo více vývojáři pracovat na souborech současně.  
  
 Project  
 Složku správy zdrojového kódu se často označuje jako projekt. To nemá žádný vztah s projekty nebo řešení v sadě Visual Studio.  
  
 Modul plug-in  
 Knihovny DLL, která poskytuje funkce správy zdrojového kódu pomocí implementace rozhraní API modulu Plug-in zdroje ovládacího prvku.  
  
 Úložiště  
 Hlavní kopie, kde systém správy zdrojových kódů uchovává historii kompletní revizi projektu. Každý projekt má přesně jedno úložiště.  
  
 Revize  
 Potvrdit změny v historii souboru nebo sady souborů. Revizi patří pořízení snímku v neustále se měnící projektu.  
  
## <a name="see-also"></a>Viz také  
 [Moduly plug-in správy zdrojového kódu](../extensibility/source-control-plug-ins.md)
