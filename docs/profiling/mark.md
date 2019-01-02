---
title: Označit | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 1d72cef3-bb09-4bbb-8864-6ea0ab623ff9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b3eec6ba541144628bf08afd79afb0bd691d1dbd
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53934807"
---
# <a name="mark"></a>Označení
*VSPerfCmd.exe* **označit** možnost vloží informace o zadaném do souboru dat profilování. Značky mohou být uvedeny v samostatných sestav VSPerfReport nebo v zobrazení sestav značky profilování uživatelského rozhraní. **Označit** slouží k určení počátečního a koncového bodu v filtry sestav a zobrazení.  
  
 **Označit** možnost musí být zadán v příkazovém řádku jedinou možností.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Mark:MarkID,[MarkName]  
```  
  
#### <a name="parameters"></a>Parametry  
 `MarkID`  
 Uživatelem definované číslo, které je uvedené jako ID značky v zobrazení profileru a sestavy. `MarkID` nemusí být jedinečný.  
  
 `MarkName`  
 (Volitelné) Uživatelem definovaný řetězec, který je uveden jako název značky v zobrazení profileru a sestavy. Pokud `MarkName` není zadán, pole název značky označit seznam je prázdný. Uzavření řetězců, které obsahují mezery nebo lomítka ("/") do uvozovek.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu vloží značku s ID 123 a název značky "TestMark".  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
VSPerfCmd.exe /Mark:123,TestMark  
```  
  
## <a name="see-also"></a>Viz také:  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil služby](../profiling/command-line-profiling-of-services.md)