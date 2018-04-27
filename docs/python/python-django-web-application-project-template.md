---
title: Šablona projektu webového rozhraní Django pro jazyk Python
description: Přehled šablony sady Visual Studio pro webové aplikace napsané v Pythonu pomocí rozhraní Django.
ms.date: 04/17/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 077619b7d47441bb4a02dbe87e7cf714b634beff
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2018
---
# <a name="django-web-project-template"></a>Šablona webového projektu Django

[Django](https://www.djangoproject.com/) je určená pro vývoj webů rychlé, zabezpečené a škálovatelné vysoké úrovně rozhraní Python. Podpora v jazyce Python v sadě Visual Studio obsahuje několik šablon projektu nastavení struktury založené na rozhraní Django webové aplikace. Chcete-li použít šablonu v sadě Visual Studio, vyberte **soubor** > **nový** > **projektu**, vyhledejte "Django" a vyberte z "prázdné Django webu Projekt,""Webový projekt Django"a"Hlasovací webový projekt Django"šablony. Najdete v článku [Learning Django kurzu](learn-django-in-visual-studio-step-01-project-and-solution.md) návod všechny šablony.

Visual Studio poskytuje úplné IntelliSense pro projekty Django:

- Proměnné kontext je předán do šablony:

    ![IntelliSense pro kontext proměnné](media/template-django-intellisense.png)

- Označování a filtrování pro obě built-ins a uživatelem definované:

    ![IntelliSense pro značky a filtry](media/template-django-intellisense-filter.png)

- Pro vložených šablon stylů CSS a JavaScript zvýrazňování syntaxe:

    ![IntelliSense šablon stylů CSS](media/template-django-intellisense-css.png)

    ![JavaScript IntelliSense](media/template-django-intellisense-js.png)

Visual Studio také poskytuje úplné [ladění podporu](debugging-python-in-visual-studio.md) pro projekty Django: 

![Zarážky](media/template-django-debugging.png)

Je obvyklé, Django projektů se mají spravovat prostřednictvím jejich `manage.py` souboru, který se předpokládá, který následuje Visual Studio. Pokud zastavíte pomocí tento soubor jako vstupní bod, v podstatě rozdělit souboru projektu. V takovém případě budete muset [znovu vytvořit projektu z existujících souborů](managing-python-projects-in-visual-studio.md#creating-a-project-from-existing-files) bez označení jako projekt Django.

## <a name="django-management-console"></a>Konzola pro správu Django

Konzola pro správu Django přistupuje prostřednictvím různých příkazy **projektu** nabídky nebo kliknutím pravým tlačítkem na projekt v Průzkumníku řešení.

- **Otevřete prostředí Django...** : otevře prostředí v kontextu vaší aplikace, která umožňuje pracovat s modely "

    ![Konzola](media/template-django-console-shell.png)

- **Django synchronizace DB**: provede `manage.py syncdb` v interaktivních okna:

    ![Konzola](media/template-django-console-sync-db.png)

- **Shromažďovat statické**: provede `manage.py collectstatic --noinput` zkopírovat všechny statické soubory do cestu určenou položkou `STATIC_ROOT` ve vaší `settings.py`. Když [publikování do služby Azure App Service](publishing-python-web-applications-to-azure-from-visual-studio.md), statické soubory jsou shromažďovány automaticky v rámci operace publikování.

    ![Konzola](media/template-django-console-collect-static.png)

- **Ověření**: provede `manage.py validate`, které sestavy všechny chyby ověřování nainstalovaný modely určeného `INSTALLED_APPS` ve vaší `settings.py`:

    ![Konzola](media/template-django-console-validate.png)

## <a name="see-also"></a>Viz také

- [Kurz Django učení](learn-django-in-visual-studio-step-01-project-and-solution.md)