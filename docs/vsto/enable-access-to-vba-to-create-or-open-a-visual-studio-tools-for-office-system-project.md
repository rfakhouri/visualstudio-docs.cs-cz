---
title: Povolit přístup pro jazyk VBA vytvořit nebo otevřít Visual Studio Tools pro projekt systému Microsoft Office
decsprition: You must explicitly enable access to the Office VBA project system before you can create or open a Visual Studio Tools for Office system project
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- vst.project.vbawrongversion
- VST.Project.VBASecurityGenericError
- VST.Project.VBASecurityPermissions
- VST.SelectDocWizard.MissingCOM
- VST.Project.VBASecurityNotSet
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 10dc439946cb209c9a8d8e0c5ff50a7e8cfe5363
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57869315"
---
# <a name="enable-access-to-vba-to-create-or-open-a-visual-studio-tools-for-the-microsoft-office-system-project"></a>Povolit přístup pro jazyk VBA vytvořit nebo otevřít Visual Studio Tools pro projekt systému Microsoft Office

Předtím, než můžete vytvořit nebo otevřít Visual Studio Tools pro Microsoft Office project system, musíte výslovně povolit přístup do jazyka Visual Basic pro systém projektu Applications (VBA) v aplikaci Microsoft Office.

 Vývojové projekty Microsoft Office vyžadují přístup do jazyka Visual Basic pro systém projektu Applications (VBA) v Microsoft Office Word a Microsoft Office Excel, i v případě, že tyto projekty nepoužívají jazyka Visual Basic pro aplikace. Podpora návrhu ovládacích prvků v obou jazyka Visual Basic a C# projektů závisí na Visual Basic pro systém projektu aplikace.

 Některé aplikace Microsoft Office – makro viry pokusí automatizace jazyka Visual Basic pro aplikace systému projektu jako prostředek k šíření sami. Když povolíte přístup do jazyka Visual Basic pro aplikace systému projektů, odebrat ochranu, která pomáhá zabránit šíření virů maker. Normální – makro zabezpečení, ale zůstává na místě, tak úroveň zabezpečení maker a seznam důvěryhodných vydavatelů, které zajišťují pro aplikace sady Office určí, zda všechna makra, běží na vašem počítači.

> [!NOTE]
> To se vztahuje pouze na vývojovém počítači. Počítačích koncových uživatelů není nutné je tato možnost povolená, které spouštějí řešení Office.

 Je důležité si uvědomit, že zakázání přístupu do jazyka Visual Basic pro systém projektu aplikace na svůj vlastní nechrání při před viry, jednoduše pomáhá zastavit některé viry rozšířilo do jiných dokumentů, pokud se počítač stane někdy nakažená hrozbou makra virů. Tato možnost je vypnuta ve výchozím nastavení jako další úroveň ochrany pro počítače, ale jeho povolení Nedovolte, aby byly v počítači více náchylné k viry pokud nedodržíte následující osvědčené postupy zabezpečení.

 Nejlepší ochranu před viry, se na spuštění při vysoké nebo velmi vysokou úroveň zabezpečení, pouze důvěřovat makrům Office ověření známých zdrojů, Office a udržovat si aktuální opravy zabezpečení a antivirové programy.

 Můžete povolit nebo zakázat možnost **důvěřovat přístup k projektu jazyka Visual Basic** ručně.

 Pokud se zobrazí chyby VBA nebo COM může opravením instalace Office.

## <a name="to-enable-or-disable-access-to-visual-basic-projects"></a>K povolení nebo zakázání přístupu k projektům Visual Basic

1. Klikněte na tlačítko **souboru** kartu.

2. Klikněte na tlačítko **možnosti**.

3. Klikněte na tlačítko **centrum**a potom klikněte na tlačítko **nastavení Centra zabezpečení**.

4. V **centrum**, klikněte na tlačítko **– makro nastavení**.

5. Zaškrtněte nebo zrušte zaškrtnutí políčka **důvěřovat přístup k objektovému modelu projektu VBA** k povolení nebo zakázání přístupu k projektům Visual Basic.

6. Klikněte na **OK**.

### <a name="to-enable-or-disable-access-to-visual-basic-projects-with-the-2007-microsoft-office-system"></a>Povolit nebo zakázat přístup k projektům jazyka Visual Basic se systémem Microsoft Office 2007

1. Na **nástroje** nabídky v aplikaci Word nebo Excel, přejděte na **– makro**a potom klikněte na tlačítko **zabezpečení**.

2. V **zabezpečení** dialogové okno, klikněte na tlačítko **Důvěryhodní vydavatelé** kartu.

3. Vyberte, chcete povolit, nebo zrušte zakázat, **důvěřovat přístup k projektu jazyka Visual Basic**.

4. Klikněte na **OK**.

## <a name="to-set-your-office-macro-security-level"></a>Chcete-li nastavit úroveň zabezpečení maker Office

1. Klikněte na tlačítko **souboru** kartu.

2. Klikněte na tlačítko **možnosti**.

3. Klikněte na tlačítko **centrum**a potom klikněte na tlačítko **nastavení Centra zabezpečení**.

4. V **centrum**, klikněte na tlačítko **– makro nastavení**.

5. V **– makro nastavení** vyberte požadované nastavení.

6. Klikněte na **OK**.

### <a name="to-set-your-office-macro-security-level-with-the-2007-microsoft-office-system"></a>Chcete-li nastavit úroveň zabezpečení maker Office pomocí systému Microsoft Office 2007

1. Na **nástroje** nabídky v aplikaci Word nebo Excel, přejděte na **– makro**a potom klikněte na tlačítko **zabezpečení**.

2. Na **úroveň zabezpečení** kartu, vyberte požadované nastavení.

    **Úroveň zabezpečení** karta obsahuje podrobnosti o jednotlivých úrovních. Další informace naleznete v tématu "Úrovni zabezpečení maker" v nápovědě sady Office.

### <a name="to-install-vba-with-the-2007-microsoft-office-system"></a>K instalaci VBA pomocí systému Microsoft Office 2007

1. V Ovládacích panelech, spusťte **přidat nebo odebrat programy** nebo **programy a funkce**.

2. Vyberte Office ve službě **aktuálně nainstalované programy** seznamu.

3. Klikněte na tlačítko **změnu**.

4. Vyberte **přidat nebo odebrat součásti**a potom klikněte na tlačítko **pokračovat**.

5. Vyberte **zvolit vlastní aplikace**a potom klikněte na tlačítko **Další**.

6. Rozbalte **sdílené součásti sady Office** v **zvolte možnosti aktualizace pro aplikace a nástroje** seznamu.

7. Otevřete rozevírací nabídku vedle **Visual Basic for Applications**a potom klikněte na tlačítko **spouštět z tohoto počítače**.

8. Klikněte na **Pokračovat**.

9. Klikněte na **Zavřít**.

## <a name="to-repair-your-installation-of-office"></a>Chcete-li opravit instalaci sady Office

1. V Ovládacích panelech, spusťte **přidat nebo odebrat programy** nebo **programy a funkce**.

2. Vyberte svou verzi Office ve službě **aktuálně nainstalované programy** seznamu.

3. Klikněte na tlačítko **změnu**.

4. Vyberte **přeinstalace nebo opravy**a potom klikněte na tlačítko **Další**.

5. Vyberte **rozpoznat a opravit chyby v instalaci Office**a potom klikněte na tlačítko **nainstalovat**.

## <a name="see-also"></a>Viz také:
- [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)