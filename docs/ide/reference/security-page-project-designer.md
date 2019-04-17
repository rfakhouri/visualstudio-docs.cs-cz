---
title: Stránka Zabezpečení, návrhář projektu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesSecurity
- vb.XBAPProjectPropertiesSecurity
helpviewer_keywords:
- Project Designer, Security page
- Security page in Project Designer
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fe78b2473fc58166edb124924673ff0c49ba92a4
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59648560"
---
# <a name="security-page-project-designer"></a>Stránka Zabezpečení, návrhář projektu

**Zabezpečení** stránku **Návrháře projektu** slouží ke konfiguraci nastavení zabezpečení přístupu kódu pro aplikace, které jsou nasazeny pomocí [!INCLUDE[ndptecclick](../../deployment/includes/ndptecclick_md.md)] nasazení. Další informace najdete v tématu [Code Access Security for ClickOnce Applications](../../deployment/code-access-security-for-clickonce-applications.md).

 Pro přístup **zabezpečení** klikněte na uzel projektu v **Průzkumníku řešení**a pak klikněte na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. Když **Návrháře projektu** se zobrazí, klikněte na tlačítko **zabezpečení** kartu.

## <a name="security-settings"></a>Nastavení zabezpečení

 **Povolení nastavení zabezpečení ClickOnce**

 Určuje, zda je povoleno nastavení zabezpečení v době návrhu. Pokud tato možnost vybrána, všechny ostatní možnosti na **zabezpečení** stránky nejsou k dispozici.

> [!NOTE]
> Když publikujete aplikaci s použitím **publikovat** průvodce, tato možnost je automaticky povolen.

 Když vyberete tuto možnost, budete mít možnost výběru mezi dvěma přepínací tlačítka: **Toto je aplikace s úplným vztahem důvěryhodnosti** nebo **Toto je aplikace s částečnou důvěryhodností**.

 Tato možnost je vybrána ve výchozím nastavení pro projekty aplikace WPF webového prohlížeče.

 Tato možnost vybrána ve výchozím nastavení pro všechny ostatní typy projektů.

 **Toto je aplikace s úplným vztahem důvěryhodnosti**

 Pokud vyberete tuto možnost, aplikace požádá o oprávnění plné důvěryhodnosti při instalaci nebo spuštění na klientském počítači. Vyhněte se použití, plné důvěryhodnosti Pokud je to možné, protože vaše aplikace budou mít stejně neomezený přístup k prostředkům, jako je například systém souborů a registr.

 Ve výchozím nastavení pro projekty aplikace WPF webového prohlížeče je tato možnost nastavená na částečném vztahu důvěryhodnosti.

 Ve výchozím nastavení pro všechny ostatní typy projektů je tato možnost nastavená na plné důvěryhodnosti.

 **Toto je aplikace s částečnou důvěryhodností**

 Pokud vyberete tuto možnost, aplikace požádá o oprávnění částečné důvěryhodnosti při instalaci nebo spuštění na klientském počítači. *Částečným vztahem důvěryhodnosti* znamená, že se spustí jenom na akce, které jsou povoleny v rámci oprávnění zabezpečení přístupu ke požadovaný kód. Další informace o tom, jak nakonfigurovat oprávnění zabezpečení naleznete v tématu [Code Access Security for ClickOnce Applications](../../deployment/code-access-security-for-clickonce-applications.md).

 Můžete zadat nastavení částečném vztahu důvěryhodnosti zabezpečení tím, že nakonfigurujete možnosti **oprávnění zabezpečení ClickOnce** oblasti.

## <a name="clickonce-security-permissions"></a>Oprávnění zabezpečení ClickOnce

 **Zóny, který aplikaci nainstaluje z**

 Určuje výchozí sadu oprávnění zabezpečení přístupu kódu. Zvolte **Internet** nebo **místní Intranet** s omezenými oprávněními nastavíte, nebo zvolte **(vlastní)** chcete konfigurovat vlastní oprávnění nastavit. Pokud aplikace požaduje více oprávnění než udělena v zóně, zobrazí se výzvy důvěryhodnosti ClickOnce koncovým uživatelům udělit další oprávnění. Další informace o tom, jak nakonfigurovat oprávnění zabezpečení naleznete v tématu [Code Access Security for ClickOnce Applications](../../deployment/code-access-security-for-clickonce-applications.md).

 Ve výchozím nastavení pro projekty aplikace WPF webového prohlížeče, je tato možnost nastavená na **Internet**.

 **Editovat XML soubor oprávnění**

 Otevře se šablona manifestu aplikace (app.manifest) ke konfiguraci oprávnění **(vlastní)** sadu oprávnění.

 **Pokročilé**

 Otevře [rozšířené zabezpečení dialogové okno nastavení](../../ide/reference/advanced-security-settings-dialog-box.md), který se používá ke konfiguraci nastavení pro ladění aplikace s omezenými oprávněními. Tato nastavení jsou kontrolovány během ladění a oprávnění výjimky signalizují, že vaše aplikace může potřebovat větší oprávnění než definované v zóně.

## <a name="see-also"></a>Viz také

- <xref:System.Security.Permissions.WebBrowserPermission>
- <xref:System.Security.Permissions.MediaPermission>
- [Zabezpečení přístupu ke kódu pro aplikace ClickOnce](../../deployment/code-access-security-for-clickonce-applications.md)
- [Postupy: Povolení nastavení zabezpečení ClickOnce](../../deployment/how-to-enable-clickonce-security-settings.md)
- [Postupy: Nastavení zóny zabezpečení pro aplikaci ClickOnce](../../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)
- [Postupy: Nastavení vlastních oprávnění pro aplikaci ClickOnce](../../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)
- [Postupy: Ladění aplikace ClickOnce s omezenými oprávněními](../../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)
- [ClickOnce – zabezpečení a nasazení](../../deployment/clickonce-security-and-deployment.md)
- [Referenční dokumentace k vlastnostem projektu](../../ide/reference/project-properties-reference.md)
- [Dialogové okno Pokročilé nastavení zabezpečení](../../ide/reference/advanced-security-settings-dialog-box.md)