---
title: MSSCCPRJ. Soubor SCC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, MSSCCPRJ.SCC file
- MSSCCPRJ.SCC file
ms.assetid: 6f2e39d6-b79d-407e-976f-b62a3cedd378
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ef076a93d27cc2c133404d6fe6463d32cb449956
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31139348"
---
# <a name="mssccprjscc-file"></a>MSSCCPRJ. Soubor SCC
Při řešení sady Visual Studio nebo projektu je umístěn ve správě zdrojového kódu pomocí rozhraní IDE, rozhraní IDE obdrží dvě důležité informace od správy zdrojového kódu ve formě řetězce modulu plug-in. Tyto řetězce "AuxPath" a "ProjName", jsou neprůhledné IDE, ale používají se modul plug-in provede najít řešení nebo projektu ve správě verzí. Prostředí IDE obvykle obdrží tyto řetězce první voláním [SccGetProjPath](../extensibility/sccgetprojpath-function.md), a je pak uloží do souboru řešení nebo produktu project pro budoucí volání [SccOpenProject](../extensibility/sccopenproject-function.md). Když vložen soubory řešení a projektu, řetězce "AuxPath" a "ProjName" se neaktualizují automaticky, když uživatel větví, větve, nebo zkopíruje soubory řešení a projektu, které jsou ve správě verzí. Abyste měli jistotu, že soubory řešení a projektu ukazují jejich správné umístění ve správě verzí, uživatelé musí ručně aktualizovat řetězce. Vzhledem k tomu, že řetězce mají být neprůhledné, nemusí být vždy zrušte způsob jejich aktualizace.  
  
 Modul plug-in zdrojového kódu můžete vyhnout tomuto problému ukládání řetězců "AuxPath" a "ProjName" ve speciální soubor s názvem MSSCCPRJ. SCC soubor. Je soubor místní, na straně klienta, které vlastní a spravuje pomocí modulu plug-in. Tento soubor je umístěn ve správě zdrojového kódu, ale je generován modul plug-in pro každý adresář, který obsahuje řízenou zdrojové soubory. Pokud chcete zjistit, které soubory jsou soubory řešení a projektu sady Visual Studio, můžete porovnat zdrojového kódu, který je modul plug-in přípony souborů standardní nebo uživatelem zadané seznam. Jakmile IDE zjistí, že podporuje modul plug-in MSSCCPRJ. Soubor SCC přestane vložení "AuxPath" a "ProjName" řetězců do řešení a soubory projektu a čte ty řetězce z MSSCCPRJ. SCC souboru místo toho.  
  
 Ovládací prvek zdroje modulu plug-in podporující MSSCCPRJ. Soubor SCC musí splňovat následující pokyny:  
  
-   Může existovat pouze jedna MSSCCPRJ. Soubor SCC každému adresáři.  
  
-   MSSCCPRJ. SCC soubor může obsahovat "AuxPath" a "ProjName" pro více souborů, které jsou v části Správa zdrojového kódu v daném adresáři.  
  
-   Řetězec "AuxPath" nesmí mít uvozovky uvnitř ho. Je povoleno mít uvozovky, do kterých ho jako oddělovače (například pár dvojité uvozovky slouží k označení prázdný řetězec). Prostředí IDE bude pruhu všechna uvozovky z řetězce "AuxPath", když je pro čtení z MSSCCPRJ. SCC soubor.  
  
-   Řetězec "ProjName" v MSSCCPRJ. SCC soubor musí odpovídat přesně řetězec vrácený z `SccGetProjPath` funkce. Pokud řetězec vrácený funkcí obsahuje uvozovky, do kterých je řetězec v MSSCCPRJ. Soubor SCC musí mít uvozovky kolem něj a naopak.  
  
-   MSSCCPRJ. SCC soubor se vytvoří nebo aktualizuje vždy, když je soubor umístěn ve správě zdrojového kódu.  
  
-   Pokud na MSSCCPRJ. Soubor SCC odstraní, zprostředkovatele by měl znovu při příštím ji provede operaci řízení zdroje týkající se tohoto adresáře.  
  
-   MSSCCPRJ. Soubor SCC musí následovat výhradně definované formátu.  
  
## <a name="an-illustration-of-the-mssccprjscc-file-format"></a>Obrázek MSSCCPRJ. Formát souboru SCC  
 Následuje ukázka MSSCCPRJ. Formát souboru SCC (čísla řádků jsou k dispozici pouze jako vodítko a by neměly být obsažené v těle souboru):  
  
 [Řádku 1] `SCC = This is a Source Code Control file`  
  
 [Řádek 2]  
  
 [Řádku 3] `[TestApp.sln]`  
  
 [Řádek 4] `SCC_Aux_Path = "\\server\vss\"`  
  
 [Řádku 5] `SCC_Project_Name = "$/TestApp"`  
  
 [Řádku 6]  
  
 [Řádku 7] `[TestApp.csproj]`  
  
 [Řádku 8] `SCC_Aux_Path = "\\server\vss\"`  
  
 [Řádku 9] `SCC_Project_Name = "$/TestApp"`  
  
 První řádek stavy účel souboru a slouží jako signaturu pro všechny soubory tohoto typu. Tento řádek by se zobrazit úplně stejně jako v všechny MSSCCPRJ. SCC soubory:  
  
 `SCC = This is a Source Code Control file`  
  
 Následuje část nastavení pro každý soubor označené podle názvu souboru do hranatých závorek. V této části se opakuje pro každý soubor sledován. Tento řádek je ukázkový název souboru, a to, `[TestApp.csproj]`. Prostředí IDE očekává následující dva řádky. Ale nedefinuje styl definovány hodnoty. Proměnné jsou `SCC_Aux_Path` a `SCC_Project_Name`.  
  
 `SCC_Aux_Path = "\\server\vss\"`  
  
 `SCC_Project_Name = "$/TestApp"`  
  
 Neexistuje žádné koncové oddělovač, který má v této části. Název souboru, stejně jako všechny literály, které se zobrazují v souboru jsou definovány v záhlaví souboru scc.h. Další informace najdete v tématu [řetězce použít jako klíče pro vyhledání modulu Plugin zdroj ovládacího prvku](../extensibility/strings-used-as-keys-for-finding-a-source-control-plug-in.md).  
  
## <a name="see-also"></a>Viz také  
 [Moduly plug-in programu zdroj ovládacího prvku](../extensibility/source-control-plug-ins.md)   
 [Řetězce, které slouží jako klíče pro vyhledání modulu plug-in pro správu zdrojového kódu](../extensibility/strings-used-as-keys-for-finding-a-source-control-plug-in.md)