---
title: 'Postupy: nastavení oprávnění | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling, setting permissions
- security [Visual Studio ALM], setting permissions
- permissions [Visual Studio ALM], profiling
- profiling tools, setting profiling permissions
- performance tools, setting profiling permissions
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1c967fd06030fcedd89d95ec22ca806549f5fed4
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845350"
---
# <a name="how-to-set-permissions"></a>Postupy: nastavení oprávnění

Tento článek popisuje, jak správce počítače uděluje oprávnění zabezpečení požadovaná pro profilace pro uživatele nebo skupiny, který nemá oprávnění správce na tomto počítači.

Princip základní zabezpečení stavy, že aplikace budou spouštět s více než oprávnění, která potřebují. Tento princip platí také pro uživatele. Pokud uživatelé mohou být plně účinná, když jsou přihlášení jako členové skupiny Users místo do skupiny Administrators, že by neměla být udělena oprávnění správce. Prvním postupu "postup vytvoření uživatelského účtu, který má uživatel oprávnění k" popisuje, jak vytvořit uživatelský účet pro člena skupiny uživatelů.

Členové skupiny uživatelé potřebovat přístup k složek a souborů na disku, které jsou sdíleny s jinými členy týmu. Druhý postup "k udělení přístupu k souborům sdílený projekt" popisuje postup udělení tohoto přístupu.

Členové skupiny uživatelů můžete spustit nástrojů pro profilaci, pokud jim správce udělí přístup k softwaru ovladače pro nástrojů pro profilaci. Poslední postup, "udělit přístup k ovladači profilování" popisuje, jak k udělení přístupu na tento ovladač.

> [!NOTE]
> Je třeba oprávnění správce k postupujte podle kroků v těchto postupech.

## <a name="to-create-a-user-account-that-has-user-permissions"></a>Chcete-li vytvořit uživatelský účet, který má oprávnění uživatele

1. Klikněte pravým tlačítkem na **Můj počítač** a pak klikněte na **spravovat**.

     **Správa počítače** otevře se okno.

2. Rozbalte položku **místní uživatelé a skupiny**.

3. Klikněte pravým tlačítkem myši **uživatelé** složku a pak klikněte na tlačítko **nového uživatele**.

     **Nového uživatele** zobrazí se dialogové okno.

4. Vyplňte pole v tomto dialogovém informacemi pro uživatelský účet, které vytváříte. Zadejte heslo. Volitelně vyberte políčko, které vyžaduje, aby uživatel změnit heslo při příštím přihlášení.

5. Klikněte na tlačítko **vytvořit** a pak klikněte na **Zavřít**.

     Nový uživatel zobrazí ve skupině uživatelů na skupinu uživatelů, kteří nemají oprávnění správce.

## <a name="to-grant-access-to-shared-project-files"></a>K udělení přístupu k sdílené soubory projektu

1. V Průzkumníku Windows (nebo v Průzkumníku souborů) vyhledejte kořenu stromu složku pro soubory projektu používá tohoto uživatele a sdílet projektový tým.

     Cesta tato složka může vypadat takto:

    ```cmd
    D:\ourProject
    ```

2. Klikněte pravým tlačítkem složku a potom klikněte na **vlastnosti**.

     **\<Název složky > vlastnosti** zobrazí se dialogové okno.

3. Klikněte **zabezpečení** kartě.

4. Klikněte na název uživatelského účtu v **skupiny nebo jméno uživatele** pole.

5. V **oprávnění pro \<uživatelské jméno >** pole, zaškrtněte políčko pro **úplné řízení**.

6. Click **OK**.

     Tím udělíte oprávnění uživatelům pro sdílenou složku stromové struktury, která začíná vybrané v kroku 5 složky.

## <a name="to-grant-access-to-the-profiling-driver"></a>Udělit přístup k ovladači profilace

1. Otevřete příkazový řádek jako správce.

2. Změňte adresář na:

    ```cmd
    <drive>:\Program Files\Microsoft Visual Studio 10\Team Tools\Performance Tools
    ```

3. Spusťte následující příkaz:

    ```cmd
    vsperfcmd /admin:driver,start /admin:service,start
    ```

     Tento příkaz nainstaluje a spustí ovladač pro nástrojů pro profilaci.

     Tento příkaz spustí profilování ovladače a služby tak, aby uživatelům bez oprávnění správce může používat profilování funkce, které jsou k dispozici v jejich místo procesu uživatele. Pouze správce může spustit příkaz; a nezdaří se pro uživatele bez oprávnění správce.

     Všimněte si, že důsledky tohoto kroku se odvolat po restartování počítače, pokud je také provést na poslední krok v tomto postupu.

4. Spusťte příkaz pro povolení přístupu k profilace ovladač funkcích podle uživatele nebo skupinu, která nemá přístup správce k počítači:

    ```cmd
    vsperfcmd /admin:security,allow,<right[,right],<user name|group name>
    ```

     Tento příkaz udělí \<uživatelské jméno > nebo \<název skupiny > účet přístup k nástrojům profilování. \<Správné > možnost určuje funkci profilování uživatel přístup. \<Správné > možnost může být jeden nebo více z následujících hodnot:

    - FullAccess – umožňuje přístup na všechny profilování metody shromažďování dat výkonu ze služeb, včetně vzorkování a křížové profilace relace.

    - SampleProfiling – umožňuje přístup k ukázkové metod profilace

    - CrossSession – umožňuje přístup k mezi relace profilace, což je vyžadováno pro profilování služeb.

5. (Volitelné) Pokud chcete zachovat výsledky předchozích kroků po restartování počítače, spusťte následující příkaz:

    ```cmd
    vsperfcmd /admin:driver,autostart,on
    ```

 Zadaní uživatelé, po přihlášení, teď bude moci používat nástrojů pro profilaci bez oprávnění správce.

## <a name="see-also"></a>Viz také:

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)  
[VSPerfCmd](../profiling/vsperfcmd.md)  
[Profilování a zabezpečení systému Windows Vista](../profiling/profiling-and-windows-vista-security.md)