---
title: Šablony položek pro projektů v jazyce Python
description: Referenční seznam šablon položek pro projekt Python, které jsou k dispozici prostřednictvím Přidat > dialogové okno novou položku v sadě Visual Studio.
ms.date: 04/25/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 9811905e842eeb62399ef3b88558ee0286b05c84
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2018
ms.locfileid: "32032812"
---
# <a name="python-item-templates"></a>Šablony položek Python

Šablony položek, které jsou k dispozici v projektů v jazyce Python prostřednictvím **projektu** > **přidat novou položku** příkaz nabídky, nebo **přidat**  >  **Novou položku** příkaz v místní nabídce v **Průzkumníku řešení**.

![Přidat novou položku – dialogové okno](media/project-item-templates.png)

Pomocí názvu zadáte pro položku, šablonu obvykle vytvoří jeden nebo více souborů a složek v aktuálně vybrané složce v projektu (pravým tlačítkem myši na složku, do které zprovoznit v místní nabídce automaticky vybere této složky). Přidání položky obsahuje v projektu Visual Studia a položka se zobrazí v **Průzkumníku řešení**.

Následující tabulka stručně popisuje účinek každé šablony položky v rámci projektu Python:

| Šablony | Vytvoří šablona |
| --- | --- |
| Soubor prázdný Python | Prázdný soubor s `.py` rozšíření. |
| Python – třída | A `.py` souboru, který obsahuje jednu definici prázdná třída Python. |
| Balíček Python | Složka, která obsahuje `__init.py__` souboru. |
| Testování částí Python | A `.py` na základě soubor s testu jedné jednotky `unittest` framework, společně s volání `unittest.main()` ke spuštění testů v souboru. |
| Stránky HTML | `.html` Souboru se strukturou jednoduchá stránka, který se skládá z `<head>` a `<body>` elementu. |
| JavaScript | Prázdná `.js` souboru. |
| Šablony stylů | A `.css` souboru, který obsahuje prázdný styl pro `body` |
| Textový soubor | Prázdná `.txt` souboru. |
| Aplikace Django 1.9<br/>Aplikace Django 1.4 | Do složky s názvem aplikace, která obsahuje soubory jádra pro aplikace Django, jak je popsáno v [Learning Django v sadě Visual Studio, krok 2-2](learn-django-in-visual-studio-step-02-create-an-app.md#step-2-1-create-an-app-with-a-default-structure) pro Django 1.9. Pro rozhraní Django 1.4 `migrations` složku, `admin.py` souboru a `apps.py` souboru nejsou zahrnuty. |
| Okno IronPython WPF | Okno WPF skládající se z dva soubory vedle sebe: `.xaml` soubor, který definuje `<Window>` s prázdnou `<Grid>` elementu a přidružené `.py` soubor, který načte souboru XAML pomocí `wpf` knihovny. Obvykle se používá v rámci projektu vytvořené pomocí jedné z šablon projektu IronPython. V tématu [Správa Python projekty - šablony projektů](managing-python-projects-in-visual-studio.md#project-templates). |
| Soubory podpory aplikace webové Role | A `bin` složku v kořenovém adresáři projektu (bez ohledu na vybranou složku v projektu). Složka obsahuje výchozí skript nasazení a `web.config` soubor pro webové role Azure Cloud Service. Také obsahuje šablony `readme.html` soubor, který vysvětluje podrobnosti. |
| Soubory podpory Role pracovního procesu | A `bin` složku v kořenovém adresáři projektu (bez ohledu na vybranou složku v projektu). Složka obsahuje výchozí nasazení a spuštění skriptu, spolu s `web.config` soubor pro role pracovního procesu Azure Cloud Service. Také obsahuje šablony `readme.html` soubor, který vysvětluje podrobnosti. |
| Azure web.config (FastCGI) | A `web.config` soubor, který obsahuje položky pro aplikace využívající [WSGI](https://wsgi.readthedocs.io/en/latest/) objekt pro zpracování příchozích připojení. Tento soubor se obvykle nasazuje do kořenového adresáře webovému serveru se službou IIS, například Azure App Service. Další informace najdete v tématu [publikování do služby Azure App Service](publishing-python-web-applications-to-azure-from-visual-studio.md). |
| Azure web.config (HttpPlatformHandler) | A `web.config` soubor, který obsahuje položky pro aplikace, které přijímat příchozí připojení na soketu. Tento soubor se obvykle nasazuje do kořenového adresáře webovému serveru se službou IIS, například Azure App Service. Další informace najdete v tématu [publikování do služby Azure App Service](publishing-python-web-applications-to-azure-from-visual-studio.md). |
| Soubor web.config Azure statické soubory | A `web.config` obvykle přidat do souboru `static` složky (nebo jiné složky obsahující statické položky) zakázat Python zpracování pro tuto složku. Tento konfigurační soubor funguje ve spojení s jedním z FastCGI nebo HttpPlatformHandler konfigurační soubory výše. Další informace najdete v tématu [publikování do služby Azure App Service](publishing-python-web-applications-to-azure-from-visual-studio.md). |
| Azure web.config vzdáleného ladění | A `web.config.debug` soubor, který umožňuje vzdálené ladění pomocí technologie WebSockets, alongside `Microsoft.PythonTools.WebRole.dll` a `ptvsd` složka, která obsahuje moduly pro nasazení na serveru, aby vzdálené ladění. Obvykle vytvoříte tuto položku na stejném místě jako vaše `web.config` souboru. Další informace najdete v tématu [vzdálené ladění kódu Python ve službě Azure](debugging-remote-python-code-on-azure.md). Také viz poznámka níže. |

> [!Note]
> Pokud přidáte ladění `web.config` šablona projektu a plánujete používat vzdálené ladění Python, musíte publikovat webu v konfiguraci "Debug". Toto nastavení je oddělená od aktuální konfigurace aktivního řešení a vždy použije jako výchozí "Verze". Pokud chcete ho změnit, otevřete **nastavení** kartě a použít **konfigurace** – pole se seznamem v Průvodci publikovat. (Viz [dokumentace k Azure](https://azure.microsoft.com/develop/python/) Další informace o vytváření a nasazení do webové aplikace Azure.)
>
> ![Změna konfigurace publikování](media/template-web-publish-config.png)

## <a name="see-also"></a>Viz také

- [Správa projektů v jazyce Python - šablony projektů](managing-python-projects-in-visual-studio.md#project-templates)
- [Šablony webových projektů jazyka Python](python-web-application-project-templates.md)
- [Publikování do služby Azure app service](publishing-python-web-applications-to-azure-from-visual-studio.md)