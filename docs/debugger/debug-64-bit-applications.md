---
title: Ladění 64bitové aplikace | Dokumentace Microsoftu
ms.date: 11/04/2016
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
ms.openlocfilehash: 6f79bd9c0f2bbf2ab3156f5bc49100c9c8aee536
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53947358"
---
# <a name="debug-64-bit-applications"></a>Ladění 64bitové aplikace
Můžete ladit 64bitovou aplikaci, na kterém běží na místním počítači nebo ve vzdáleném počítači.  
  
 Chcete-li ladit 64bitovou aplikaci, která běží na vzdáleném počítači, naleznete v tématu [vzdálené ladění](../debugger/remote-debugging.md).  
  
 Ladění 64bitové aplikace místně, Visual Studio používá 64-bit pracovním procesem (msvsmon.exe) k provádění operací nízké úrovně, které nelze provést uvnitř 32bitový proces sady Visual Studio.  
  
 Ladění ve smíšeném režimu není podporováno pro 64bitové procesy, které používají rozhraní .NET Framework verze 3.5 nebo starší.  
  
## <a name="debug-a-64-bit-application"></a>Ladění 64bitové aplikace  
 Vyzkoušet ladění 64bitové aplikace:  
  
1.  Vytvoření řešení sady Visual Studio, například C# konzolové aplikace.  
  
2.  Nastavte konfiguraci do 64-bit pomocí nástroje Configuration Manager. Další informace najdete v tématu [jak: Konfigurace projektů pro cílové platformy](../ide/how-to-configure-projects-to-target-platforms.md).  
  
3.  V tomto okamžiku začne 64bitovou verzi vzdáleného ladicího programu (msvsmon.exe). Spuštění, dokud je otevřené řešení pomocí konfigurace 64bitové.  
  
4.  Spusťte ladění. Stejně jako u 32-bit konfigurace byste měli mít stejné prostředí. Pokud dojde k chybám, najdete v článku níže v části řešení potíží.  
  
## <a name="troubleshooting-64-bit-debugging"></a>Řešení potíží s 64bitové ladění  
 Může se zobrazit chyba: "Operaci ladicí 64bitových trvá déle, než se očekávalo." V takovém případě sada Visual Studio odeslal žádost o 64bitové verze msvsmon.exe a vždycky trvalo dlouhou dobu pro výsledek žádosti k téhle akci vrátit.  
  
 Existují dva hlavní příčiny této chyby:  
  
-   Máte síťové zabezpečení softwaru nainstalovaného v počítači, který způsobil síťového zásobníku je nespolehlivý, a klesla paketů prostřednictvím místního hostitele. Zkuste zakázat veškerého softwaru zabezpečení sítě a podívejte se, pokud to vyřeší. Pokud ano, sestavy pro dodavatele softwaru zabezpečení sítě, který software je v konfliktu s provozem localhost.  
  
-   Spustíte na výkon nebo zablokování problém se sadou Visual Studio. Pokud tento problém nastává pravidelně, můžete shromažďovat výpisy sady Visual Studio (devenv.exe) a pracovním procesem (msvsmon.exe) a odesílat do Microsoftu. Informace o vytváření sestav problému najdete v tématu [postup ohlášení problému se sadou Visual Studio](../ide/How-to-Report-a-Problem-with-Visual-Studio-2017.md).
  
## <a name="see-also"></a>Viz také  
 [64bitové aplikace](https://docs.microsoft.com/dotnet/framework/64-bit-apps)   
 [Konfigurace programů pro 64bitové prostředí](/cpp/build/configuring-programs-for-64-bit-visual-cpp)   
 [Podpora 64bitové integrované vývojové prostředí sady Visual Studio](../ide/visual-studio-ide-64-bit-support.md)   
 [Použití souborů výpisu paměti](../debugger/using-dump-files.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)