---
title: 'Postupy: Určení dalších možností instrumentace | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.property.advanced
helpviewer_keywords:
- instrumentation, options
- profiling tools, session options
- performance sessions, options
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4e93a249572c34d801426b9919a274aa133639a3
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54963720"
---
# <a name="how-to-specify-additional-instrumentation-options"></a>Postupy: Určení dalších možností instrumentace

Vám umožňuje instrumentovat binárních souborů pomocí integrovaného vývojového prostředí sady Visual Studio nebo pomocí nástrojů příkazového řádku. Pokud jste instrumentovali binární soubor z integrovaného vývojového prostředí, můžete určit objem dat shromážděných během instrumentace zadáním dalších možností instrumentace do [VSInstr](../profiling/vsinstr.md) nástroj. Tyto možnosti jsou dostupné na cílové úrovni nebo relace. Například pokud chcete zahrnout nebo vyloučit určité funkce během procesu instrumentace, použijte možnost Další instrumentaci na cílové úrovni.

> [!IMPORTANT]
> Každý test, který je vložen mírně změní chování původního programu. Tato změna způsobí, že režii během analýzy. I když je odečtena aproximaci Tato dodatečná režie, má stále drobným časování dopady na aplikací s více vlákny. [VSInstr](../profiling/vsinstr.md) možnosti nápovědy řízení shromažďování dat během profilace nástroj.

## <a name="to-specify-additional-instrumentation-option"></a>Chcete-li určit možnost Další instrumentace

1. V **prohlížeč výkonu**, vyberte **relace výkonu** a pak klikněte pravým tlačítkem a vyberte **vlastnosti**.

2. V **stránky vlastností**, klikněte na tlačítko **Upřesnit** vlastnosti.

3. Zadejte možnosti **dalších možností instrumentace** pole.

     Například použijte /CONTROL:THREAD k určení profilování úrovně. Úplný seznam možností najdete v tématu [VSInstr](../profiling/vsinstr.md).

4. Klikněte na **OK**.

## <a name="see-also"></a>Viz také:

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)  
[Profil z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)