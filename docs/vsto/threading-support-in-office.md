---
title: Dělení na vlákna podpory v Office
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- multiple threads [Office development in Visual Studio]
- threading [Office development in Visual Studio]
- Office applications [Office development in Visual Studio], threading support
- object models [Office development in Visual Studio], threading support
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f5c2a0a8623228091e2acee184fa0272c2bbf311
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37059330"
---
# <a name="threading-support-in-office"></a>Dělení na vlákna podpory v Office
  Tento článek obsahuje informace o tom, jak dělení na vlákna je podporována v modelu objektů aplikace Microsoft Office. Objektový model Office není bezpečné pro přístup z více vláken, ale je možné pracovat s více vlákny v řešení Office. Aplikace Office jsou servery modelu COM (Component Object). COM umožňuje klientům volání COM serverů na libovolný vláken. U serverů modelu COM, které nejsou bezpečné pro přístup z více vláken poskytuje COM mechanismus k serializaci souběžných volání tak, aby pouze jedno vlákno logické spustí na serveru kdykoli. Tento mechanismus se označuje jako model single-threaded apartment (STA). Vzhledem k tomu, že se serializují volání, mohou být blokovány volající za období, zatímco server je zaneprázdněn nebo je zpracování jiná volání na vlákna na pozadí.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="knowledge-required-when-using-multiple-threads"></a>Znalostní báze vyžaduje při používání více vláken  
 Chcete-li pracovat s více vláken, musí mít alespoň základní znalosti o následujících charakteristik ve více vláken:  
  
-   Rozhraní API systému Windows  
  
-   COM s více vlákny koncepty  
  
-   Souběžnost  
  
-   Synchronizace  
  
-   Zařazování  
  
 Obecné informace o více vláken, viz [dělení na spravovaná vlákna](/dotnet/standard/threading/).  
  
 Office běží v hlavní STA Vysvětlení důsledků to umožní pochopit, jak používat více vláken s Office.  
  
## <a name="basic-multithreading-scenario"></a>Základní scénář více vláken  
 Na hlavní vlákna uživatelského rozhraní vždycky spuštění kódu v řešeních pro systém Office. Můžete chtít vyhlazení výkonu aplikací při spuštění samostatných úloh na vlákna na pozadí. Cílem je k dokončení úlohy dvou zdánlivě najednou místo jednu úlohu a potom jinými, což má za následek hladší provádění (hlavním důvodem pro použití více vláken). Například může mít kód událostí na hlavního vlákna uživatelského rozhraní aplikace Excel a na vlákna na pozadí můžete spustit úlohu, která shromažďuje data ze serveru a aktualizace buněk v uživatelském rozhraní aplikace Excel s daty ze serveru.  
  
## <a name="background-threads-that-call-into-the-office-object-model"></a>Vlákna na pozadí, které volají do modelu objektu Office  
 Pokud vlákna na pozadí provede volání aplikace Office, volání je automaticky zařazen přes hranice STA. Však není zaručeno, že aplikace Office může zpracovat volání v době, že umožňuje vlákně na pozadí. Existuje několik možností:  
  
1.  Aplikace Office musí čerpadla zprávy pro volání mít příležitost k zadání. Pokud je to těžký zpracování bez je to může trvat dobu.  
  
2.  Pokud jiné logické vlákno je již v typu apartment, nelze zadat nové vlákno. Často se to stane, když logické vlákno zadá aplikace Office a potom provádí vícenásobné volání zpět do objektu apartment volajícího. Aplikace se zablokuje čekáním na toto volání vrátit.  
  
3.  Aplikace Excel může být ve stavu, tak, že nemůže zpracovat okamžitě příchozího hovoru. Například aplikace Office může být zobrazení modální dialogové okno.  
  
 Pro možnosti 2 a 3 poskytuje COM [IMessageFilter](/windows/desktop/api/objidl/nn-objidl-imessagefilter) rozhraní. Pokud jej na server, implementuje všechna volání zadejte prostřednictvím [HandleIncomingCall](/windows/desktop/api/objidl/nf-objidl-imessagefilter-handleincomingcall) metoda. Pro možnost 2 jsou automaticky zamítnuty volání. Pro možnost 3 můžete server odmítnout volání, v závislosti na v případech. Pokud se odmítne volání, musíte se rozhodnout co dělat, volající. Za normálních okolností implementuje volající [IMessageFilter](/windows/desktop/api/objidl/nn-objidl-imessagefilter), v takovém případě byste dostali upozornění o zamítnutí pomocí [RetryRejectedCall](/windows/desktop/api/objidl/nf-objidl-imessagefilter-retryrejectedcall) metoda.  
  
 Ale v případě řešení vytvořená pomocí nástrojů pro vývoj pro Office v sadě Visual Studio, zprostředkovatel komunikace s objekty COM převede všechny odmítnuté volání <xref:System.Runtime.InteropServices.COMException> ("filtr zpráv označená, že aplikace je zaneprázdněn"). Vždy, když provedete objektový model volání vlákna na pozadí, musíte být připraveni pro zpracování této výjimky. Obvykle, který zahrnuje opakování pro určitou dobu a pak zobrazení dialogového okna. Můžete však také vytvořit vlákně na pozadí jako STA a potom proveďte registraci filtr zpráv pro toto vlákno případě.  
  
## <a name="start-the-thread-correctly"></a>Spustit vlákno správně  
 Když vytvoříte nové vlákno STA, nastavte stav objektu apartment na STA před zahájením vlákno. Následující příklad kódu ukazuje, jak to udělat.  
  
 [!code-csharp[Trin_VstcoreCreatingExcel#5](../vsto/codesnippet/CSharp/Trin_VstcoreCreatingExcelCS/ThisWorkbook.cs#5)]
 [!code-vb[Trin_VstcoreCreatingExcel#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreCreatingExcelVB/ThisWorkbook.vb#5)]  
  
 Další informace najdete v tématu [dělení na spravovaná vlákna osvědčené postupy](/dotnet/standard/threading/managed-threading-best-practices).  
  
## <a name="modeless-forms"></a>Nemodální formulářů  
 Nemodální formulář umožňuje nějaký typ interakce s aplikací, když je formulář zobrazen. Uživatel komunikuje formulář a formulář komunikuje s aplikací bez ukončovací. Objektový model Office podporuje spravované nemodální formuláře; však by neměl být použili v vlákna na pozadí.  
  
## <a name="see-also"></a>Viz také:  
 [Dělení na spravovaná vlákna](/dotnet/standard/threading/)  
 [Dělení na vlákna (C#)](/dotnet/csharp/programming-guide/concepts/threading/index) [vlákna (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/threading/index)   
 [Použití vláken a dělení na vlákna](/dotnet/standard/threading/using-threads-and-threading)   
 [Návrh a vytvoření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)  
  
  