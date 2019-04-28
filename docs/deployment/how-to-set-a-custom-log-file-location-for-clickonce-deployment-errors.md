---
title: 'Postupy: Nastavení vlastního umístění souboru protokolu pro chyby nasazení ClickOnce | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- troubleshooting ClickOnce deployments
- ClickOnce deployment, troubleshooting
- ClickOnce deployment, error logging
ms.assetid: 77424414-7f0e-4b99-94bb-ea130de92d09
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9e247034b22b7fef8e83235cc6666d282720a219
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63406696"
---
# <a name="how-to-set-a-custom-log-file-location-for-clickonce-deployment-errors"></a>Postupy: Nastavení umístění souboru vlastního protokolu pro chyby nasazení ClickOnce
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] udržuje aktivace soubory protokolu pro všechna nasazení. Tyto protokoly zdokumentujte jakékoli chyby týkající se instalace a inicializace [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení. Ve výchozím nastavení [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] vytvoří jeden soubor protokolu pro každé nasazení aktivace. Ukládá tyto soubory protokolu ve složce dočasných souborů Internetu. Soubor protokolu pro nasazení se zobrazí uživateli, když dojde k selhání aktivace a uživatel klikne **podrobnosti** ve výsledné dialog s chybou.

 Toto chování lze změnit pro konkrétního klienta pomocí Editoru registru (**regedit.exe**) Chcete-li nastavit cestu k souboru vlastního protokolu. V takovém případě [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] protokoly aktivace úspěchů a neúspěchů pro všechna nasazení v jednom souboru.

> [!CAUTION]
> Pokud Editor registru používán správně, můžete způsobit vážné problémy, které mohou vyžadovat přeinstalaci operačního systému. Pomocí Editoru registru na vlastní nebezpečí.

> [!NOTE]
> Je potřeba zkrátit nebo odstranění souboru protokolu čas od času, aby se zabránilo jejímu růstu příliš velký.

 Následující postup popisuje, jak nastavit vlastního umístění souboru protokolu pro jednoho klienta.

### <a name="to-set-a-custom-log-file-location"></a>Chcete-li nastavit vlastního umístění souboru protokolu

1. Otevřít **Regedit.exe**.

2. Přejděte na uzel `HKCU\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment`.

3. Nastavte hodnotu řetězce `LogFilePath` úplnou cestu a název souboru váš vlastní protokol upřednostňované umístění.

     Toto umístění musí být v adresáři, do které má uživatel oprávnění k zápisu. Například v systému Windows Vista, vytvořte následující strukturu složek a nastavení `LogFilePath` k *C:\Users\\\<uživatelské jméno > \Documents\Logs\ClickOnce\installation.log*.

## <a name="see-also"></a>Viz také:
- [Řešení potíží s nasazením ClickOnce](../deployment/troubleshooting-clickonce-deployments.md)