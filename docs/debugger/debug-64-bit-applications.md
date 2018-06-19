---
title: Ladění 64bitových aplikací | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], 64-bit
- 64-bit debugging
ms.assetid: db648e5f-6375-4e2d-aa98-eb7261958927
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 17577684c7adffe46326d2151710e88745c60e1f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31461435"
---
# <a name="debug-64-bit-applications"></a>Ladění 64bitových aplikací
Můžete ladit 64bitová verze aplikace, která běží na místním počítači nebo ve vzdáleném počítači.  
  
 K ladění 64bitové aplikaci, která běží na vzdáleném počítači, najdete v části [vzdálené ladění](../debugger/remote-debugging.md).  
  
 K ladění 64bitových aplikací místně, Visual Studio použije 64-bit pracovní proces (msvsmon.exe) k provedení operace nízké úrovně, které není možné v rámci procesu 32bitová verze sady Visual Studio.  
  
 Ladění ve smíšeném režimu není podporována pro 64bitové procesy, které používají rozhraní .NET Framework verze 3.5 nebo dřívější.  
  
## <a name="debug-a-64-bit-application"></a>Ladění aplikace s 64-bit  
 Pokusit ladění 64bitových aplikací:  
  
1.  Vytvoření řešení Visual Studio, například C# konzolové aplikace.  
  
2.  Nastavte konfiguraci na 64-bit pomocí nástroje Configuration Manager. Další informace najdete v tématu [postupy: Konfigurace projektů pro cílové platformy](../ide/how-to-configure-projects-to-target-platforms.md).  
  
3.  V tomto okamžiku 64bitové verze vzdáleného ladicího programu (msvsmon.exe) spustí. Spustí, pokud je otevřen řešení s konfigurací 64-bit.  
  
4.  Spusťte ladění. Stejně jako u 32-bit konfigurace byste měli mít stejné prostředí. Pokud dojde k chybám, projděte si část Poradce při potížích s níže.  
  
## <a name="troubleshooting-64-bit-debugging"></a>Řešení potíží při ladění 64-bit  
 Mohou se zobrazit chyba: "operaci ladění 64-bit trvá déle, než se očekávalo." V takovém případě Visual Studio odeslal žádost na 64bitové verzi msvsmon.exe a trvá dlouho výsledek tohoto požadavku opět online.  
  
 Existují dvě hlavní příčiny této chyby:  
  
-   Máte nainstalován ve vašem počítači, který způsobil síťový zásobník být nespolehlivé mezi sítě software zabezpečení a klesla paketů prostřednictvím místního hostitele. Zkuste, zákaz veškerého softwaru zabezpečení sítě a zjistěte, zda tato nevyřeší. Pokud ano, sestavy na svého dodavatele softwaru zabezpečení sítě, který softwaru je v konfliktu s přenosy localhost.  
  
-   Je spuštěn na výkon nebo zablokování problém pomocí sady Visual Studio. Pokud k problému dochází k pravidelné, můžete shromažďovat výpisy Visual Studio (devenv.exe) a pracovní proces (msvsmon.exe) a jejich odeslání společnosti Microsoft. Informace o vytváření sestav k problému najdete v tématu [postup nahlásit problém pomocí sady Visual Studio](../ide/How-to-Report-a-Problem-with-Visual-Studio-2017.md).
  
## <a name="see-also"></a>Viz také  
 [64bitové aplikace](http://msdn.microsoft.com/Library/fd4026bc-2c3d-4b27-86dc-ec5e96018181)   
 [Konfigurace programů pro 64bitové prostředí](/cpp/build/configuring-programs-for-64-bit-visual-cpp)   
 [Podpora 64bitových technologií sady Visual Studio IDE](../ide/visual-studio-ide-64-bit-support.md)   
 [Použití souborů výpisu paměti](../debugger/using-dump-files.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)