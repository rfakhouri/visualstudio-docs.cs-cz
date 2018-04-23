---
title: Zabezpečení přístupu ke kódu pro aplikace ClickOnce | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- vb.XBAPProjectPropertiesSecurity.HowTo
- vb.XBAProjectPropertiesSecurity.HowTo
- vb.ProjectPropertiesSecurity.HowTo
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [ClickOnce], security
- ClickOnce applications, caspol
- security [ClickOnce], WPF browser-hosted applications
- security [ClickOnce], ClickOnce applications
- ClickOnce applications, code access security policies
- security, ClickOnce
ms.assetid: 04b104d0-0bd3-4ccb-b164-1de92d234487
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dad9b3c8391c54c4d668a4c695f4f459664ef373
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="code-access-security-for-clickonce-applications"></a>Zabezpečení přístupu ke kódu pro aplikace ClickOnce
Aplikace ClickOnce jsou založené na rozhraní .NET Framework a podléhají omezením zabezpečení přístupu kódu. Z tohoto důvodu je důležité, že rozumíte důsledkům kód zabezpečení přístupu k a odpovídajícím způsobem zápisu aplikace ClickOnce.  
  
 Zabezpečení přístupu kódu je mechanismus v rozhraní .NET Framework, který pomáhá omezit přístup k chráněným prostředkům a operace. Byste měli nakonfigurovat oprávnění zabezpečení přístupu kódu pro aplikace ClickOnce k používání oblasti vhodné pro umístění instalačního programu aplikace. Ve většině případů můžete **Internet** zónu pro omezenou sadu oprávnění nebo **místní Intranet** zóny pro větší oprávnění.  
  
## <a name="default-clickonce-code-access-security"></a>Zabezpečení přístupu kódu ClickOnce výchozí  
 Ve výchozím nastavení obdrží aplikací ClickOnce úplná oprávnění, pokud je nainstalovat nebo spustit na klientském počítači.  
  
-   Aplikace, která má oprávnění úplné důvěryhodnosti má neomezený přístup k prostředkům, například systém souborů a registr. Umožňuje potenciálně zneužití škodlivý kód aplikace (a systému koncového uživatele).  
  
-   Pokud aplikace vyžaduje plná oprávnění, koncový uživatel může zobrazit výzva k udělení oprávnění k aplikaci. To znamená, že aplikace neposkytuje skutečně možnosti ClickOnce a řádku potenciálně může být matoucí pro méně zkušené uživatele.  
  
    > [!NOTE]
    >  Při instalaci aplikace z vyměnitelného média, například na disku CD-ROM, není zadání. Správce sítě a kromě toho můžete nakonfigurovat zásady sítě tak, aby uživatelé nebyli vyzýváni při instalaci aplikace z důvěryhodného zdroje. Další informace najdete v tématu [Přehled nasazení důvěryhodných aplikací](../deployment/trusted-application-deployment-overview.md).  
  
 Pokud chcete omezit oprávnění pro aplikace ClickOnce, můžete upravit oprávnění zabezpečení přístupu kódu pro aplikaci na vyžádání oblasti, která nejlépe odpovídá oprávnění, která vaše aplikace vyžaduje. Ve většině případů můžete vybrat zóny, ze kterého je aplikace nasazená. Například pokud podniková aplikace je aplikace, můžete použít **místní Intranet** zóny. Pokud je aplikace internetovou aplikaci, můžete použít **Internet** zóny.  
  
## <a name="configuring-security-permissions"></a>Konfigurace oprávnění zabezpečení  
 Vždy byste měli nakonfigurovat aplikaci ClickOnce k vyžádání příslušnou zónu a omezit oprávnění zabezpečení přístupu kódu. Můžete nakonfigurovat oprávnění zabezpečení na **zabezpečení** stránky **Návrhář projektu**.  
  
 **Zabezpečení** stránku **Návrhář projektu** obsahuje **povolení nastavení zabezpečení ClickOnce** zaškrtávací políčko. Pokud toto políčko je vybraná, požadavky na oprávnění zabezpečení jsou přidány do manifest nasazení pro vaši aplikaci. Během instalace bude se uživateli výzva k udělení oprávnění, pokud požadovaná oprávnění překročí výchozí oprávnění pro zónu, ve kterém je aplikace nasazená. Další informace najdete v tématu [postupy: povolení nastavení zabezpečení ClickOnce](../deployment/how-to-enable-clickonce-security-settings.md).  
  
 Aplikace nasazené z různých míst mají různé úrovně oprávnění bez zobrazení výzvy. Například v případě, že je aplikace nasazená z Internetu, obdrží vysoce omezující sadu oprávnění. Při instalaci z místní Intranet, obdrží další oprávnění, a při instalaci z disku CD-ROM, obdrží oprávnění plné důvěryhodnosti.  
  
 Jako výchozí bod pro konfiguraci oprávnění, můžete vybrat ze zóny zabezpečení **zóny** na seznamu **zabezpečení** stránky. Pokud vaše aplikace bude nasazena potenciálně z více než jednu zónu, vyberte zónu s nejnižší oprávnění. Další informace najdete v tématu [postupy: nastavení zóny zabezpečení pro aplikaci ClickOnce](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md).  
  
 Vlastnosti, které lze nastavit lišit podle sady oprávnění; Ne všechny sady oprávnění mají konfigurovatelné vlastnosti. Další informace o úplný seznam oprávnění, které aplikace může požadovat najdete v tématu <xref:System.Security.Permissions>. Další informace o tom, jak nastavit oprávnění pro vlastní zóny najdete v tématu [postupy: nastavení vlastních oprávnění pro aplikaci ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md).  
  
## <a name="debugging-an-application-that-has-restricted-permissions"></a>Ladění aplikace, který má omezená oprávnění  
 Jako vývojář s největší pravděpodobností spusťte vývojovém počítači s oprávnění plné důvěryhodnosti. Proto se nezobrazí stejné výjimky zabezpečení při ladění aplikace, které uživatelé mohou vidět při jejich spuštění s omezenými oprávněními.  
  
 Aby bylo možné zachytit tyto výjimky, budete muset ladění aplikace se stejnými oprávněními jako koncový uživatel. Ladění s omezenými oprávněními, může být povoleno na **zabezpečení** stránky **Návrhář projektu**.  
  
 Při ladění aplikace s omezenými oprávněními, výjimky, bude vyvolána pro všechny požadavky zabezpečení kódu povolené na **zabezpečení** stránky. Zobrazí se pomocníka výjimka, poskytování návrhy o tom, jak upravit kód, aby se zabránilo výjimku.  
  
 Kromě toho při psaní kódu zakáže funkci IntelliSense v editoru kódu žádné členy, které nejsou součástí oprávnění zabezpečení, které jste nakonfigurovali.  
  
 Další informace najdete v tématu [postupy: ladění aplikace ClickOnce s omezenými oprávněními](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md).  
  
## <a name="security-permissions-for-browser-hosted-applications"></a>Oprávnění zabezpečení pro aplikace hostované prohlížečem  
 Visual Studio poskytuje následující typy projektů pro aplikace Windows Presentation Foundation (WPF):  
  
-   Aplikaci Windows WPF  
  
-   Aplikace WPF webového prohlížeče  
  
-   Knihovna vlastních ovládacích prvků WPF  
  
-   Knihovna Service WPF  
  
 Z těchto typů projektu pouze WPF webové prohlížeče aplikace hostované ve webovém prohlížeči a proto vyžaduje speciální nasazení a nastavení zabezpečení. Výchozí nastavení zabezpečení pro tyto aplikace jsou následující:  
  
-   **Povolení nastavení zabezpečení ClickOnce**  
  
-   **Toto je aplikace s částečnou důvěryhodností**  
  
-   **Zónu Internetu** (s výchozí nastavení pro WPF aplikace webového prohlížeče vybrali oprávnění)  
  
 V **Upřesnit nastavení zabezpečení** dialogové okno, **ladění tuto aplikaci s vybraným nastavením oprávnění** zaškrtávací políčko je vybraná a zakázat. To je proto ladění v zóně nelze vypnout pro webové aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Postupy: povolení nastavení zabezpečení ClickOnce](../deployment/how-to-enable-clickonce-security-settings.md)   
 [Postupy: nastavení zóny zabezpečení pro aplikace ClickOnce](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [Postupy: nastavení vlastních oprávnění pro aplikaci ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Postupy: ladění aplikace ClickOnce s omezenými oprávněními](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [Přehled nasazení důvěryhodných aplikací](../deployment/trusted-application-deployment-overview.md)   
 [Stránka Zabezpečení, Návrhář projektu](../ide/reference/security-page-project-designer.md)