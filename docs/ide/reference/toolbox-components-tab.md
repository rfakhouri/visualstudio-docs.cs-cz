---
title: "Sada nástrojů, karta součásti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Toolbox, Components tab
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: cf0ab13b104422771b117c17ed3ff89b53fa461f
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="toolbox-components-tab"></a>Sada nástrojů, karta Součásti

Zobrazí součásti, které můžete přidat do jazyka Visual Basic a C# Designer. Kromě součásti rozhraní .NET Framework, které jsou součástí sady Visual Studio, jako <xref:System.Messaging.MessageQueue> a <xref:System.Diagnostics.EventLog> součásti, můžete přidat vaše vlastní nebo jiných součástí na této kartě.
  
 Zobrazené na této kartě **zobrazení** nabídce vyberte možnost **sada nástrojů**. V **sada nástrojů**, vyberte **součásti** kartě.  
  
 **BackgroundWorker –**  
 Vytvoří `System.ComponentModel.BackgroundWorker` instanci komponenty, která se může spustit operací na vlákno oddělené, vyhrazené.  
  
 **Položka DirectoryEntry**  
 Vytvoří <xref:System.DirectoryServices.DirectoryEntry> instanci komponenty, který zapouzdřuje uzel nebo objekt z hierarchie služby Active Directory a slouží k interakci s poskytovatelé služeb Active Directory.  
  
 **DirectorySearcher**  
 Vytvoří <xref:System.DirectoryServices.DirectorySearcher> instanci komponenty, které můžete použít k provedení dotazy pro službu Active Directory.  
  
 **ErrorProvider**  
 Vytvoří `System.Windows.Forms.ErrorProvider` instanci komponenty, které označuje pro koncového uživatele, že ovládací prvek na formuláři došlo k chybě s ním spojená.  
  
 **EventLog**  
 Vytvoří <xref:System.Diagnostics.EventLog> instanci komponenty, které můžete použít k interakci se systémem a vlastní protokoly událostí, včetně zápisu události do protokolu a načítání dat protokolu. Další informace najdete v tématu [Úvod do protokolu událostí komponenty](http://msdn.microsoft.com/en-us/a2ba4f28-4b1a-435e-99ef-51b28e21f805).  
  
 **FileSystemWatcher**  
 Vytvoří <xref:System.IO.FileSystemWatcher> instanci komponenty, které můžete použít k monitorování se změní na všechny adresář nebo soubor, ke které máte přístup. Další informace najdete v tématu [postupy: Konfigurace instancí komponent FileSystemWatcher](http://msdn.microsoft.com/en-us/2e628234-4951-4135-8a86-28b924070d50).  
  
 **HelpProvider –**  
 Vytvoří `System.Windows.Forms.HelpProvider` instanci komponenty, která poskytuje místní nebo online nápovědy pro ovládací prvky.  
  
 **ImageList**  
 Vytvoří `System.Windows.Forms.ImageList` instanci komponenty, který poskytuje metody pro správu kolekce `System.Drawing.Image` objekty.  
  
 **MessageQueue**  
 Vytvoří <xref:System.Messaging.MessageQueue> instanci komponenty, které můžete použít k interakci se fronty zpráv, včetně čtení zpráv z a zápis zpráv do fronty, zpracování transakcí a provádění úloh správy fronty. Další informace najdete v tématu [pomocí součásti zasílání zpráv](http://msdn.microsoft.com/en-us/922dbac7-26f0-4e39-b666-ccfc184793d7).  
  
 **PerformanceCounter**  
 Vytvoří <xref:System.Diagnostics.PerformanceCounter> instanci komponenty, které můžete použít k interakci se čítačů výkonu systému Windows, včetně vytváření nových kategorií a instance, čtení hodnoty z čítačů a provádění výpočtů na data čítače. Další informace najdete v tématu [monitorování prahové hodnoty výkonu](http://msdn.microsoft.com/en-us/b8b44a55-31d0-4b45-9517-8c1b1e4fdc91).  
  
 **Proces**  
 Vytvoří <xref:System.Diagnostics.Process> instance komponenty můžete použít k zastavení, spuštění a manipulaci data související s procesy ve vašem systému. Další informace najdete v tématu [monitorování a Správa procesů systému Windows](http://msdn.microsoft.com/en-us/a86bd4c1-b92c-49a0-8f32-61d67837b45e).  
  
 **SerialPort**  
 Vytvoří `System.IO.Ports.SerialPort` instanci komponenty, která poskytuje synchronní a událostmi řízené vstupně-výstupních operací, přístup k PIN kódu a zalomení stav a přístup k vlastnostem sériového zařízení.  
  
 **ServiceController**  
 Vytvoří <xref:System.ServiceProcess.ServiceController> instanci komponenty, které můžete použít k manipulaci s stávající služby, včetně spouštět a zastavovat služby a odesílání příkazů k nim. Další informace najdete v tématu [monitorování služby systému Windows](http://msdn.microsoft.com/en-us/4542ee3f-e052-4cb9-8726-58e9420de222).  
  
 **Timer**  
 Vytvoří <xref:System.Windows.Forms.Timer> instanci komponenty, které můžete použít k přidání funkcí založené na čase do aplikací systému Windows. Další informace najdete v tématu [komponenta časovač](/dotnet/framework/winforms/controls/timer-component-windows-forms).  
  
> [!NOTE]
>  K dispozici je také systém založen <xref:System.Timers.Timer> , můžete přidat do **sada nástrojů** to <xref:System.Timers.Timer> je optimalizovaná pro serverové aplikace a systém Windows Forms <xref:System.Windows.Forms.Timer> je nejvhodnější pro použití na Windows Forms.  
  
## <a name="see-also"></a>Viz také  
 [Programování s komponentami](http://msdn.microsoft.com/Library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)   
 [Součást programování návody](http://msdn.microsoft.com/Library/373cacf7-479e-4b05-991c-5cb18824e913)   
 [Toolbox](../../ide/reference/toolbox.md)   
 [Výběr dialogové okno položek sady nástrojů (Visual Studio)](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb)