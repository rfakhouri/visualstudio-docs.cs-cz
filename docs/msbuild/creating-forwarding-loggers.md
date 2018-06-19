---
title: Vytváření předávání protokolovacích nástrojů | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, forwarding loggers
- MSBuild, logging
ms.assetid: 3aebf9c8-b62c-4cb2-b2d6-8cdfcd369a24
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b95b0725e0cbb3a7568e51298fb83f05b74f18fb
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31568637"
---
# <a name="creating-forwarding-loggers"></a>Vytváření předávajících (sekundárních) protokolovacích nástrojů
Předávání protokolovacích nástrojů zvýšit efektivitu protokolování umožňují zvolit události, kterou chcete sledovat, když vytváříte projekty v systému s více procesory. Když povolíte předávání protokolovacích nástrojů, můžete zabránit nežádoucí události z zahltí centrální protokolovacího nástroje zpomalení čase vytvoření buildu a zbytečného protokolu.  
  
 Chcete-li vytvořit protokolovacího nástroje předávání, můžete buď implementace <xref:Microsoft.Build.Framework.IForwardingLogger> rozhraní a potom implementovat její metody ručně nebo použít <xref:Microsoft.Build.BuildEngine.ConfigurableForwardingLogger> třídy a její předem nakonfigurovaná metody. (K tomu postačí pro většinu aplikací.)  
  
## <a name="register-events-and-respond-to-them"></a>Registrace události a reagovat na ně  
 Protokolovač předávání shromažďuje informace o událostí sestavení udávaný rutinou sekundární sestavení modul, který je pracovní proces, který je vytvořen pomocí procesu hlavní sestavení během vytváření sestavení v systému s více procesory. Protokolovač předávání vybere události předávání do centrální protokolovacího nástroje podle pokynů, které jste zadali.  
  
 Je nutné zaregistrovat předávání protokolovacích nástrojů pro zpracování události, které chcete monitorovat. K registraci pro události, musí přepsat protokolovacích nástrojů <xref:Microsoft.Build.Utilities.Logger.Initialize%2A> metoda. Tato metoda nyní zahrnuje volitelný parametr `nodecount`, který může být nastavena na počet procesorů v systému. (Výchozí hodnota je 1.)  
  
 Příklady událostí můžete sledovat <xref:Microsoft.Build.Framework.IEventSource.TargetStarted>, <xref:Microsoft.Build.Framework.IEventSource.ProjectStarted>, a <xref:Microsoft.Build.Framework.IEventSource.ProjectFinished>.  
  
 V prostředí s více procesory jsou zprávy o událostech pravděpodobně k přijetí mimo pořadí. Proto musíte vyhodnotit události pomocí obslužné rutiny události v předávání protokolovacího nástroje a program ji k určení události, které mají být předána do přesměrovače za účelem předání do centrální protokolovacího nástroje. K tomu můžete použít <xref:Microsoft.Build.Framework.BuildEventContext> třídy, který je připojen k každou zprávu, aby bylo možné identifikovat události chcete předat dál, a pak předejte názvy události, které <xref:Microsoft.Build.BuildEngine.ConfigurableForwardingLogger> – třída (nebo podtřídou třídy ji). Při použití této metody není vyžadováno dopředného události žádné jiné konkrétní kódování.  
  
## <a name="specify-a-forwarding-logger"></a>Zadejte přesměrování protokoly  
 Poté, co byl zkompilován protokolovacího nástroje předávání do sestavení, se musí zjistit [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] k použití při sestavení. Chcete-li to provést, použijte `/FileLogger`, `/FileLoggerParameters`, a `/DistributedFileLogger` přepínačů s MSBuild.exe. `/FileLogger` Přepínač informuje MSBuild.exe, zda je přímo připojena protokolovacího nástroje. `/DistributedFileLogger` Přepínač znamená, že je soubor protokolu na jeden uzel. K nastavení parametrů na předávání protokolovač, použijte `/FileLoggerParameters` přepínače. Další informace o těchto a dalších MSBuild.exe přepínače najdete v tématu [Reference k příkazovému řádku](../msbuild/msbuild-command-line-reference.md).  
  
## <a name="multi-processor-aware-loggers"></a>Více-procesorů protokolovacích nástrojů  
 Při sestavování projektu na systému s více procesory, nejsou automaticky prokládaný zprávy sestavení na každý procesor v jednotném pořadí. Místo toho je potřeba vytvořit zprávu seskupení s prioritou pomocí <xref:Microsoft.Build.Framework.BuildEventContext> třídu, která je připojena k každé zprávě. Další informace o vytváření více procesorů, najdete v části [protokolování v prostředí s více procesory](../msbuild/logging-in-a-multi-processor-environment.md).  
  
## <a name="see-also"></a>Viz také  
 [Získávání protokolů o sestavení](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [Protokolovací nástroje sestavení](../msbuild/build-loggers.md)   
 [Protokolování v prostředí s více procesory](../msbuild/logging-in-a-multi-processor-environment.md)