---
title: "Postupy: určení dalších možností instrumentace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.property.advanced
helpviewer_keywords:
- instrumentation, options
- profiling tools, session options
- performance sessions, options
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 8052c0538619588f60fd21802209d57bd7fdf80d
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2018
---
# <a name="how-to-specify-additional-instrumentation-options"></a>Postupy: Určení dalších možností instrumentace

Můžete instrumentace binárních souborů pomocí prostředí Visual Studio IDE, nebo pomocí nástroje příkazového řádku. Pokud jste instrumentace binárního souboru z integrovaného vývojového prostředí, můžete řídit objem dat, které jsou shromážděny během instrumentace zadáním dalších možností instrumentace na [vsinstr –](../profiling/vsinstr.md) nástroj. Tyto možnosti jsou dostupné na úrovni cíl nebo relace. Například pokud chcete zahrnout nebo vyloučit konkrétní funkce během procesu instrumentace, použijte parametr další instrumentace na cílové úrovni.

> [!IMPORTANT]
> Každý test, který je vložen mírně změní chování programu původní. Tato úprava způsobí, že režii během analýzy. I když je odečten sblížení Tato dodatečná režie, má stále jemně časování důsledky pro vícevláknové aplikace. [Vsinstr –](../profiling/vsinstr.md) nástroj Možnosti nápovědy řízení shromažďování dat při vytváření profilu.

## <a name="to-specify-additional-instrumentation-option"></a>Chcete-li určit možnost Další instrumentace

1. V **prohlížeč výkonu**, vyberte **výkonnostní relace** a potom klikněte pravým tlačítkem a vyberte **vlastnosti**.

2. V **vlastnosti stránky**, klikněte **Upřesnit** vlastnosti.

3. Zadejte možnosti v **dalších možností instrumentace** pole.

     /CONTROL:THREAD můžete například použijte k určení profilování úrovně. Úplný seznam možností najdete v tématu [vsinstr –](../profiling/vsinstr.md).

4. Click **OK**.

## <a name="see-also"></a>Viz také

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)  
[Profilace z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)