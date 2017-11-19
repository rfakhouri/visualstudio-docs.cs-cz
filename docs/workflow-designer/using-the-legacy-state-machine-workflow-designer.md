---
title: "Pomocí Návrháře pracovního postupu starší stavu počítače | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- StateFinalizationActivity activity
- StateActivity activity
- SetStateActivity activity
- EventDrivenActivity activity
- state machine workflow designer
- state machine workflows, designer
- state machine workflows, activities
- StateInitializationActivity activity
ms.assetid: 2cd21123-35c2-4eaf-82f6-86fce7a8f04d
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3eefde445f5c8aca7199d4316472fe92c3160d00
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="using-the-legacy-state-machine-workflow-designer"></a>Pomocí Návrháře pracovního postupu starší stav počítače
Když vytvoříte nový projekt workflow stavu počítače v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] , která se zaměřuje buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)], můžete použít buď **stavu počítače pracovního postupu konzolové aplikace** nebo  **Stav pracovního postupu knihovna počítačů** šablona starší verze projektu. Pokud si zvolíte jednu z těchto šablon projektu stavu počítače, zobrazí se jako návrháře uživatelské rozhraní starší verze návrháře stav počítače. Informace o šablonách projektů starší verze stavu počítače najdete v tématu [postupy: vytvoření stavu počítače pracovního postupu konzolové aplikace (zastaralé)](../workflow-designer/how-to-create-state-machine-workflow-console-applications-legacy.md) a [postupy: vytvoření stavu počítače pracovního postupu knihovny (starší)](../workflow-designer/how-to-create-a-state-machine-workflow-library-legacy.md).  
  
 Pracovní postup stavového stroje se skládá ze sady stavy. Jeden stav je označené jako počáteční stav. Každý stav, může přijímat sadu událostí. Založené na události, může být proveden přechod na jiný stav. Pracovní postup stavového stroje může mít do konečného stavu. Když je proveden přechod do konečného stavu, dokončení pracovního postupu.  
  
## <a name="state-machine-designer-views"></a>Návrhář zobrazení stavu počítače  
 Návrhář stavu počítače je volného tvaru návrháře, což znamená, že aktivity lze přesunout volně na návrhovou plochu. Návrhář počítač stav má dvě zobrazení: *stavu* zobrazení a *událostmi řízené* zobrazení.  
  
 Zobrazení stavu zobrazuje stav aktivity a aktivity založeného na událostech, které může být obsažený v rámci stavu aktivity. V tomto zobrazení představují přechody z jednoho stavu do jiného řádky, které rozšiřují z aktivity založeného na událostech v jeden stav na jiný stav. Můžete také vytvořit přechody nakreslení čáry. Kreslení přechodu, vyberte aktivitu založeného na událostech a vyberte jednu z obslužné rutiny na aktivity a přetáhněte ji. Tato akce nakreslí čáru. Tento řádek přiřazen stav cíl, označující přechod mezi stavy.  
  
 Pro přístup k události řízené zobrazení, klikněte dvakrát na aktivitu založeného na událostech. Návrhář, který se zobrazí je podobné jako u návrháře sekvenční pracovní postup. V horní části návrháře navigační panel zobrazuje hierarchii aktivity až událostmi řízené aktivity, která se zobrazí. Kliknutím na libovolný element, v zobrazené hierarchii, můžete přejít zpět na zobrazení stavu. Pokud mají vykreslovat přechod z jednoho stavu do druhého v zobrazení stavu, a pokud jsou zobrazení událostí řízené zobrazení této aktivity, stav aktivitu sady je přidána do aktivity událostmi řízené za vás. Pokud změníte vlastnosti sady stavu aktivity, se projeví zpět v zobrazení stavu.  
  
## <a name="state-machine-workflow-activities"></a>Aktivity pracovního postupu stavu počítače  
 Následující tabulka popisuje klíčové aktivity, které se používají v Návrháři pracovních postupů stav počítače.  
  
|Název sady nástrojů|Aktivita|Popis|  
|------------------|--------------|-----------------|  
|**Stav**|[StateActivity](http://go.microsoft.com/fwlink?LinkID=65042)|Představuje stav stavového počítače; může obsahovat další **StateActivity** aktivity. Další informace najdete v tématu [pomocí aktivity StateActivity](http://go.microsoft.com/fwlink?LinkID=65083).|  
|**Setstate –**|[SetStateActivity](http://go.microsoft.com/fwlink?LinkID=65041)|Určuje přechod na nový stav. Další informace najdete v tématu [pomocí aktivity SetStateActivity](http://go.microsoft.com/fwlink?LinkID=65082).|  
|**Aktivitu typu StateInitialization**|[StateInitializationActivity](http://go.microsoft.com/fwlink?LinkID=65044)|Provede, když se zadá stavu; může obsahovat jiné aktivity. Další informace najdete v tématu [pomocí aktivity aktivitu typu StateInitialization](http://go.microsoft.com/fwlink?LinkID=65006).|  
|**Aktivitu typu StateFinalization**|[StateFinalizationActivity](http://go.microsoft.com/fwlink?LinkID=65043)|Provede obsažené aktivity při opuštění [StateActivity](http://go.microsoft.com/fwlink?LinkID=65042) aktivity. Další informace najdete v tématu [pomocí aktivity StateFinalizationActivity](http://go.microsoft.com/fwlink?LinkID=65008).|  
|**Aktivitu typu EventDriven**|[EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65029)|Použít pro stavy, které jsou závislé na externí události, která spustí provádění. **EventDrivenActivity** aktivity musí mít aktivitu, která implementuje [IEventActivity](http://go.microsoft.com/fwlink?LinkID=65032) rozhraní jako první podřízené aktivity. Další informace najdete v tématu [pomocí aktivity EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65068).|  
  
 Hlavní komponenty v pracovním postupu stavu počítač je [StateActivity](http://go.microsoft.com/fwlink?LinkID=65042) aktivity. Jak na různých místech v pracovním postupu počítač stavu zaznamenání události, různých stavů jsou zadány pro zpracování úloh, které jsou přidružené události. Pracovní postup může během relace pracovního postupu, nechte a zadejte několik různých stavů. Tyto stavy připojit k sobě navzájem pomocí [SetStateActivity](http://go.microsoft.com/fwlink?LinkID=65041) aktivity.  
  
 Při přetažení novou **StateActivity** na návrhovou plochu pracovního postupu můžete přidat [EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65029), [StateInitializationActivity](http://go.microsoft.com/fwlink?LinkID=65044), [ StateFinalizationActivity](http://go.microsoft.com/fwlink?LinkID=65043), nebo další **StateActivity** aktivity jako podřízené aktivity.  
  
> [!CAUTION]
>  Při vytváření pracovních postupů pomocí návrháře pracovních postupů stavu počítače, je třeba sledovat strukturu pracovního postupu vytváření návrhu **Osnova dokumentu** okno zobrazení. Zobrazení struktury pracovní postup stavového stroje v **Osnova dokumentu** zobrazení okna zrcadlí logické rozložení aktivity v souboru pracovního postupu značek. Fyzické rozložení aktivit pracovního postupu jako zobrazí se na návrhovou plochu, která nemusí zrcadlení logické rozložení aktivity v souboru pracovního postupu značek.  
>   
>  Otevřete **Osnova dokumentu** okno na **zobrazení** nabídky, přejděte na příkaz **ostatní okna**a potom vyberte **Osnova dokumentu**.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytváření stavu počítače pracovního postupu konzolových aplikací (zastaralé)](../workflow-designer/how-to-create-state-machine-workflow-console-applications-legacy.md)   
 [Postupy: vytvoření knihovny stavu počítače pracovního postupu (zastaralé)](../workflow-designer/how-to-create-a-state-machine-workflow-library-legacy.md)   
 [Pracovní postupy stavu počítače](http://go.microsoft.com/fwlink?LinkID=65016)   
 [Pomocí aktivity StateActivity](http://go.microsoft.com/fwlink?LinkID=65083)   
 [Pomocí aktivity StateInitializationActivity](http://go.microsoft.com/fwlink?LinkID=65006)   
 [Pomocí aktivity StateFinalizationActivity](http://go.microsoft.com/fwlink?LinkID=65008)   
 [Pomocí aktivity SetStateActivity](http://go.microsoft.com/fwlink?LinkID=65082)   
 [Pomocí aktivity EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65068)