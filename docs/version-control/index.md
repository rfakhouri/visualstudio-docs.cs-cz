---
layout: LandingPage
title: "Správa verzí v sadě Visual Studio | Služby VSTS & TFS"
description: "Průvodce Začínáme se službou správy verzí v sadě Viual Studio"
keywords: "Služby VSTS, sady TFS, Správa verzí"
author: steved0x
ms.manager: douge
ms.author: sdanie
ms.date: 12/15/2017
ms.topic: landing-page
ms.prod: .net-core
ms.assetid: 2c119a5f-0272-48c0-8d6c-806196944aea
ms.workload:
- multiple
ms.openlocfilehash: 428139af8680bc60f4456367d1a17d4c97874efc
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="version-control-in-visual-studio"></a>Správa verzí v sadě Visual Studio

Systémy kontroly verze můžete sledovat změny v kódu v čase. Při provádění změn systému správy verzí pořídí snímek vašich souborů. Systém správy verzí uloží tento snímek trvale, takže pokud to potřebujete ho můžete odvolat později. Visual Studio poskytuje [Git](/vsts/git/index) a [Team Foundation verze ovládacího prvku (TFVC)](/vsts/tfvc/index). Při rozhodování mezi těmito dvěma systémy, najdete v části [výběru ovládacího prvku správnou verzi pro váš projekt](/vsts/tfvc/comparison-git-tfvc?toc=/visualstudio/version-control/toc.json&bc=/vsts/git/breadcrumb/vc/toc.json).

## <a name="git"></a>Git
Git je systém správy nejčastěji používaných verzí dnes a rychle stává standard pro správu verzí. Git je distribuovaný systém správy verzí, což znamená, že vaše místní kopii kódu je ovládací prvek úložiště úplnou verzi. Zkontrolujte tyto plně funkční místní úložiště, které je snadné práce offline nebo vzdáleně. Potvrdit práci místně a potom synchronizovat vaší kopie úložiště, ve kterém se bude pro kopii na serveru. Tato zlepší se liší od centralizované verzí, které klienti musí synchronizovat kód s serveru před vytvořením nové verze kódu.

<ul class="panelContent cardsFTitle">
    <li>
        <a href="https://www.visualstudio.com/learn-git/">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img width="48" height="48" alt="" src="https://docs.microsoft.com/media/common/i_git-mark.svg" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Seznámení s Gitem</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="/vsts/git/share-your-code-in-git-vs-2017?toc=/visualstudio/version-control/toc.json&bc=/vsts/git/breadcrumb/vc/toc.json">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img width="48" height="48" alt="" src="https://docs.microsoft.com/media/common/i_git-mark.svg" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Začínáme s Gitem pomocí sady Visual Studio</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="/vsts/git/tutorial/clone?toc=/visualstudio/version-control/toc.json&bc=/vsts/git/breadcrumb/vc/toc.json">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img width="48" height="48" alt="" src="https://docs.microsoft.com/media/common/i_git-mark.svg" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Klonovat existující úložiště Git</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
</ul>

## <a name="tfvc"></a>TFVC

Team Foundation – správa verzí (TFVC) je centralizovaný systém správy verzí. Členové týmu mají zpravidla ve svých vývojových počítačích pouze jednu verzi každého souboru. Historická data se udržují pouze na serveru. Větve jsou založeny na cestě a vytvořeny na serveru.

<ul class="panelContent cardsFTitle">
    <li>
        <a href="/vsts/tfvc/overview">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img width="48" height="48" alt="" src="https://docs.microsoft.com/media/logos/logo_visual-studio.svg" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Další informace TFVC</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="/vsts/tfvc/share-your-code-in-tfvc-vs?toc=/visualstudio/version-control/toc.json&bc=/vsts/git/breadcrumb/vc/toc.json">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img width="48" height="48" alt="" src="https://docs.microsoft.com/media/logos/logo_visual-studio.svg" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Začínáme s TFVC v sadě Visual Studio</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
   <li>
        <a href="/vsts/tfvc/get-code-reviewed-vs?toc=/visualstudio/version-control/toc.json&bc=/vsts/git/breadcrumb/vc/toc.json">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img width="48" height="48" alt="" src="https://docs.microsoft.com/media/logos/logo_visual-studio.svg" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Zkontrolujte váš kód</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
</ul>


## <a name="resources"></a>Prostředky 

- [Pro adresáře Git](https://git-scm.com/book/en/v2)  
- [Plánování migrace na Git](https://www.visualstudio.com/learn/centralized-to-git/)  
- [Migrace z TFVC do Git](https://www.visualstudio.com/learn/migrate-from-tfvc-to-git/)  

 

