---
title: Sada nástrojů, karta součásti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- Toolbox, Components tab
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: aa91db706d7e1236162ef69e6fd31e791ed44dbb
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="toolbox-components-tab"></a>Sada nástrojů, karta Součásti

Zobrazí součásti, které můžete přidat do jazyka Visual Basic a C# Designer. Kromě součásti rozhraní .NET Framework, které jsou součástí sady Visual Studio, jako <xref:System.Messaging.MessageQueue> a <xref:System.Diagnostics.EventLog> součásti, můžete přidat vaše vlastní nebo jiných součástí na této kartě.
  
 Zobrazené na této kartě **zobrazení** nabídce vyberte možnost **sada nástrojů**. V **sada nástrojů**, vyberte **součásti** kartě.  
  
 **BackgroundWorker**  
 Vytvoří `System.ComponentModel.BackgroundWorker` instanci komponenty, která se může spustit operací na vlákno oddělené, vyhrazené.  
  
 **DirectoryEntry**  
 Vytvoří <xref:System.DirectoryServices.DirectoryEntry> instanci komponenty, který zapouzdřuje uzel nebo objekt z hierarchie služby Active Directory a slouží k interakci s poskytovatelé služeb Active Directory.  
  
 **DirectorySearcher**  
 Vytvoří <xref:System.DirectoryServices.DirectorySearcher> instanci komponenty, které můžete použít k provedení dotazy pro službu Active Directory.  
  
 **ErrorProvider**  
 Vytvoří `System.Windows.Forms.ErrorProvider` instanci komponenty, které označuje pro koncového uživatele, že ovládací prvek na formuláři došlo k chybě s ním spojená.  
  
 **EventLog**  
 Vytvoří <xref:System.Diagnostics.EventLog> instanci komponenty, které můžete použít k interakci se systémem a vlastní protokoly událostí, včetně zápisu události do protokolu a načítání dat protokolu.
  
 **FileSystemWatcher**  
 Vytvoří <xref:System.IO.FileSystemWatcher> instanci komponenty, které můžete použít k monitorování se změní na všechny adresář nebo soubor, ke které máte přístup.
  
 **HelpProvider**  
 Vytvoří `System.Windows.Forms.HelpProvider` instanci komponenty, která poskytuje místní nebo online nápovědy pro ovládací prvky.  
  
 **ImageList**  
 Vytvoří `System.Windows.Forms.ImageList` instanci komponenty, který poskytuje metody pro správu kolekce `System.Drawing.Image` objekty.  
  
 **MessageQueue**  
 Vytvoří <xref:System.Messaging.MessageQueue> instanci komponenty, které můžete použít k interakci se fronty zpráv, včetně čtení zpráv z a zápis zpráv do fronty, zpracování transakcí a provádění úloh správy fronty.

 **PerformanceCounter**  
 Vytvoří <xref:System.Diagnostics.PerformanceCounter> instanci komponenty, které můžete použít k interakci se čítačů výkonu systému Windows, včetně vytváření nových kategorií a instance, čtení hodnoty z čítačů a provádění výpočtů na data čítače.
  
 **Proces**  
 Vytvoří <xref:System.Diagnostics.Process> instance komponenty můžete použít k zastavení, spuštění a manipulaci data související s procesy ve vašem systému.
  
 **SerialPort**  
 Vytvoří `System.IO.Ports.SerialPort` instanci komponenty, která poskytuje synchronní a událostmi řízené vstupně-výstupních operací, přístup k PIN kódu a zalomení stav a přístup k vlastnostem sériového zařízení.  
  
 **ServiceController**  
 Vytvoří <xref:System.ServiceProcess.ServiceController> instanci komponenty, které můžete použít k manipulaci s stávající služby, včetně spouštět a zastavovat služby a odesílání příkazů k nim.
  
 **Timer**  
 Vytvoří <xref:System.Windows.Forms.Timer> instanci komponenty, které můžete použít k přidání funkcí založené na čase do aplikací systému Windows. Další informace najdete v tématu [komponenta časovač](/dotnet/framework/winforms/controls/timer-component-windows-forms).  
  
> [!NOTE]
>  K dispozici je také systém založen <xref:System.Timers.Timer> , můžete přidat do **sada nástrojů** to <xref:System.Timers.Timer> je optimalizovaná pro serverové aplikace a systém Windows Forms <xref:System.Windows.Forms.Timer> je nejvhodnější pro použití na Windows Forms.  
  
## <a name="see-also"></a>Viz také

[Programování s komponentami](http://msdn.microsoft.com/Library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)  
[Součást programování návody](http://msdn.microsoft.com/Library/373cacf7-479e-4b05-991c-5cb18824e913)  
[Panel nástrojů](../../ide/reference/toolbox.md)