---
title: "Odkaz na službu – dialogové okno Konfigurace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- msvse_wcf.dlg.ConfigureServiceReference
helpviewer_keywords:
- WCF services, Configure Service Reference dialog box
- service references [Visual Studio], configuring behavior
- Configure Service Reference dialog box
ms.assetid: 25e4c36b-2db6-4e71-9010-b7068255d09d
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: b3b9ae8406845de886009da981eaf7f63e68972b
ms.sourcegitcommit: 49aa031cbebdd9c7ec070c713afb1a97d1ecb701
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2018
---
# <a name="configure-service-reference-dialog-box"></a>Dialogové okno Nastavit odkaz na službu

**Nastavit odkaz na službu** dialogové okno umožňuje konfigurovat chování služby Windows Communication Foundation (WCF).

> [!NOTE]
> Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, vyberte v nabídce Nástroje pro nastavení importu a exportu. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).

Pro přístup k **nastavit odkaz na službu** dialogové okno, klikněte pravým tlačítkem na může služba odkaz v **Průzkumníku řešení** a zvolte **nastavit odkaz na službu**. Můžete také přístup k dialogu kliknutím **Upřesnit** tlačítka na **přidat služby odkaz dialogové okno**.

## <a name="task-list"></a>Seznam úloh  
  
-   Chcete-li změnit adresu, která je hostitelem služby WCF, zadejte nové adresy v **adresu** pole.  
  
-   Pokud chcete změnit úroveň přístupu pro třídy v klientovi WCF, vyberte úroveň přístupu klíčové slovo v **přístup úroveň pro vygenerované třídy** seznamu.  
  
-   Asynchronní volání metody služby WCF, vyberte **Generovat asynchronní operace** zaškrtávací políčko.  
  
-   Chcete-li vygenerovat typy kontraktů zpráv v klienta WCF, vyberte **vždy generovat kontrakty zpráv** zaškrtávací políčko.  
  
-   Typy kolekcí seznamu nebo slovník pro klienta WCF, vyberte typy z **– typ kolekce** a **– typ kolekce slovníku** uvádí.  
  
-   Chcete-li vypnout sdílení typu, zrušte **znovu použít typy v odkazovaných sestaveních** zaškrtávací políčko. Chcete-li povolit sdílení typu pro podmnožinu odkazovaná sestavení, vyberte **znovu použít typy v odkazovaných sestaveních** zaškrtněte políčko **znovu použít typy v odkazovaných sestaveních**a vyberte požadovanou odkazy na v **odkazovaný seznam sestavení**.  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Adresa**  
 Použít k aktualizaci webovou adresu, kde odkazu na službu hledá službu. Například během vývoje služby může být hostovaný na serveru vývoj pak později přesunout na provozním serveru vyžadující změnu adresy.  
  
> [!NOTE]
>  Address element není k dispozici při **nastavit odkaz na službu** dialogové okno se zobrazí z **přidat Service Reference Dialog Box**.  
  
 **Úroveň přístupu pro vygenerované třídy**  
 Určuje úroveň přístupu třídy klienta WCF v kódu.  
  
> [!NOTE]
>  Pro projekty webových stránek, je tato možnost vždycky nastavený na `Public` a nelze je změnit. Další informace najdete v tématu [řešení potíží s odkazy na službu](../data-tools/troubleshooting-service-references.md).  
  
 **Generovat asynchronní operace**  
 Určuje, zda synchronně bude volat metody služby WCF (výchozí) nebo asynchronně.  
  
 **Generování operací založený na úlohách**  
 Při psaní kódu pro asynchronní, tato možnost umožňuje využívat nástroje Task Parallel Library (TPL) byla zavedena s .net 4. V tématu [úkolů Parallel Library (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl).  
  
 **Vždy generovat kontrakty zpráv**  
 Určuje, zda typy kontraktů zpráv se budou generovat pro klienta WCF. Další informace o kontrakty zpráv najdete v tématu [pomocí kontrakty zpráv](/dotnet/framework/wcf/feature-details/using-message-contracts).  
  
 **Typ kolekce**  
 Určuje typ kolekce seznamu pro klienta WCF. Je výchozím typem <xref:System.Array>.  
  
 **Slovník – typ kolekce**  
 Určuje typ kolekce slovníku pro klienta WCF. Je výchozím typem <xref:System.Collections.Generic.Dictionary%602>.  
  
 **Znovu použít typy v odkazovaných sestaveních**  
 Určuje, zda klienta WCF se pokusí znovu použít, již existuje v odkazovaných sestaveních namísto generování nových typů, když je služba přidán nebo aktualizován. Ve výchozím nastavení je toto políčko zaškrtnuto.  
  
 **Znovu použít typy v odkazovaných sestaveních pro všechny**  
 Pokud vybraná, všechny typy v **odkazovaný seznam sestavení** bude znovu použita Pokud je to možné. Ve výchozím nastavení je tato možnost vybrána.  
  
 **Znovu použít typy v odkazovaných sestaveních**  
 Při výběru pouze vybrané typy v **odkazovaný seznam sestavení** bude znovu použita.  
  
 **Seznam odkazovaná sestavení**  
 Obsahuje seznam odkazovaná sestavení projektu nebo webu. Když **znovu použít typy v odkazovaných sestaveních** je vybraná, jednotlivá sestavení může být vybrána nebo vymazána.  
  
 **Přidat odkaz na Web** zobrazí dialogové okno Přidat odkaz na Web.

> [!NOTE]
> Tuto možnost byste měli použít pouze pro projekty, které používají verzi 2.0 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].

> [!NOTE]
> **Přidat odkaz na Web** tlačítko je dostupné pouze tehdy, když **nastavit odkaz na službu** dialogové okno se zobrazí z **přidat služby odkaz dialogové okno**.

## <a name="see-also"></a>Viz také

[Postupy: Přidání odkazu na webovou službu](how-to-add-update-or-remove-a-wcf-data-service-reference.md)  
[Služby Windows Communication Foundation a služby WCF Data Services v sadě Visual Studio](../data-tools/configure-service-reference-dialog-box.md)