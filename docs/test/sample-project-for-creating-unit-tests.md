---
title: Ukázkový kód pro testování částí
description: Tento článek obsahuje ukázkový kód, který může být testována pomocí jednotkových testů v sadě Visual Studio.
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: sample
helpviewer_keywords:
- unit test sample [Visual Studio]
- unit tests, samples
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 839aeb7028608c60b2cd2f4170d37b06e3973f55
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
---
# <a name="sample-code-for-testing"></a>Ukázkový kód pro testování

Tento ukázkový kód obsahuje třídu, *BankAccont*, pomocí různých metod, které může být testována pomocí testování částí.

Kód se používá v následující kurzy:

- [Vytváření a spouštění testování částí pro spravovaný kód](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md). Tento názorný postup vás provede kroky pro vytváření a přizpůsobení testování částí, jejich spuštění a podívejte se na výsledky testu.
- [Pomocí nástroje příkazového řádku testovací](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867). V tomto návodu můžete pomocí nástroje příkazového řádku MSTest.exe spouštět testy a zobrazit výsledky.

## <a name="sample-code"></a>Ukázkový kód

Pouze touto úmyslnou chybou v této ukázce je, že metodu v debetní "m_balance += částka" by měl mít minus, není plus přihlášení před symbolem rovná se.

```csharp
using System;

namespace BankAccountNS
{
    /// <summary>
    /// Bank Account demo class.
    /// </summary>
    public class BankAccount
    {
        private string m_customerName;

        private double m_balance;

        private bool m_frozen = false;

        private BankAccount()
        {
        }

        public BankAccount(string customerName, double balance)
        {
            m_customerName = customerName;
            m_balance = balance;
        }

        public string CustomerName
        {
            get { return m_customerName; }
        }

        public double Balance
        {
            get { return m_balance; }
        }

        public void Debit(double amount)
        {
            if (m_frozen)
            {
                throw new Exception("Account frozen");
            }

            if (amount > m_balance)
            {
                throw new ArgumentOutOfRangeException("amount");
            }

            if (amount < 0)
            {
                throw new ArgumentOutOfRangeException("amount");
            }

            m_balance += amount; // intentionally incorrect code
        }

        public void Credit(double amount)
        {
            if (m_frozen)
            {
                throw new Exception("Account frozen");
            }

            if (amount < 0)
            {
                throw new ArgumentOutOfRangeException("amount");
            }

            m_balance += amount;
        }

        private void FreezeAccount()
        {
            m_frozen = true;
        }

        private void UnfreezeAccount()
        {
            m_frozen = false;
        }

        public static void Main()
        {
            BankAccount ba = new BankAccount("Mr. Bryan Walton", 11.99);

            ba.Credit(5.77);
            ba.Debit(11.22);
            Console.WriteLine("Current balance is ${0}", ba.Balance);
        }
    }
}
```

/ * Společností, organizací, produktů, názvů domén, e-mailové adresy, loga, osoby, místa a události použité v ukázkách jsou smyšlené. Žádné spojení se skutečnou společností, organizace, produktu, název domény, e-mailovou adresu, logem, osoba, místech nebo události je určený nebo událostmi. \*/

## <a name="create-the-project"></a>Vytvoření projektu

Pro práci s tímto kódem, nejprve vytvořte projekt pro něj v sadě Visual Studio. Postupujte podle kroků pro vytvoření projektu v [návod: vytváření a spouštění testování částí pro spravovaný kód](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#create-a-project-to-test).

## <a name="see-also"></a>Viz také

- [Návod: Vytváření a spouštění testování částí pro spravovaný kód](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)
- [Návod: Použití nástroje testů z příkazového řádku](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867)
