---
title: Skapa ett Azure Storage-konto och ett nyckelvalv
description: I det här avsnittet beskrivs hur du skapar ett Azure Storage-konto och nyckelvalv.
author: gionoder
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 2786d350fde2399aadb35dc653bc15123e0e6d91
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893812"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a>Skapa ett Azure Storage-konto och ett nyckelvalv

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a>Förutsättningar

Innan du kan slutföra stegen i det här ämnet måste du se till att följande uppgifter har slutförts:

- Skapa en nyckelvalvresurs i Azure. Mer information om mått finns i [Om Azure Key Vault](/azure/key-vault/general/overview).
- Skapa ett Azure Storage-konto (Blob Storage). Mer information finns i [Underhålla Azure Storage-kontot](/azure/storage/blobs/).

## <a name="overview"></a>Översikt

I det här avsnittet ska du utföra två huvudsteg:

- Konfigurera Azure Storage-kontot för att hämta lagringskontots URI.
- Ställ in nyckelvalvet för att lagra lagringskontots URI.

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a>Konfigurera Azure Storage-kontot för att hämta lagringskontots URI

1. Öppna det lagringskonto som du vill använda med tillägget e-fakturering.
2. Gå till **Blob Service** \> **Behållare** och skapa en ny behållare.
3. Ange ett namn på behållaren och ställ in fältet **Offentlig åtkomstnivå** på **Privat (ingen anonym åtkomst)**.
4. Öppna behållaren och gå till **Inställningar \> Åtkomstpolicy**.
5. Välj **Lägg till policy** om du vill lägga till en lagrad åtkomstpolicy.
6. Ange fältet **Identifierare** och **Behörigheter** efter behov. I fältet **Behörigheter** bör du välja alla behörigheter.

    ![Bevilja behörighet för Blob Storage](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. Ange start- och utgångsdatum. Utgångsdatumet måste vara i framtiden.
8. Klicka på **OK** om du vill spara policy och spara sedan ändringarna i behållaren.
9. Gå tillbaka till lagringskontot och öppna **Lagringsutforskaren (förhandsversion)**.
10. Högerklicka på behållaren och välj sedan **Hämta signatur för delad åtkomst**.
11. I dialogrutan **Signatur för delad åtkomst** kopiera och spara värdet **URI**. Det här värdet används i nästa procedur och kallas för *Signatur för delad åtkomst URI*.

    ![Markera och kopiera URI-värdet](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a>Ställ in nyckelvalvet för att lagra lagringskontots URI

1. Öppna det nyckelvalv som du vill använda med e-fakturering.
2. Gå till **Inställning** \> **Hemligheter** och välj sedan **Generera/importera** om du vill skapa en ny hemlighet.
3. På sidan **Skapa en hemlighet** i fältet **Överföringsalternativ** välj **Manuell**.
4. Ange namnet på hemligheten. Det här namnet används under installationen av tjänsten i RCS (Regulatory Configuration Service) och kommer att kallas *nyckelvalvets hemliga namn*.
5. I fältet **Värde** markera **Signatur för delad åtkomst URI** och välj sedan **Skapa**.
6. Ställ in åtkomstprincipen så att e-fakturering på den korrekta nivån för säker åtkomst till den hemlighet som du har skapat. Gå till **Inställningar \> Åtkomstprinciper** och välj **Lägg till åtkomstprincip**.
7. Ange de hemliga behörigheterna för åtgärderna **Hämta** och **Lista**.

    ![Bevilja tjänståtkomst](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. Ange certifikatbehörigheter för åtgärderna **Hämta** och **Lista**.

    ![Bevilja certifikatbehörighet](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. I fältet **Välj huvudkonto**, välj **Inget valt**.
10. I dialogrutan **Primär** välj primär genom att lägga till **Tjänst för e-fakturering**.
11. Välj **Lägg till** och välj sedan **Spara ändringar i nyckelvalv**.
12. På sidan **Översikt** kopiera värdet **DNS-namn** för nyckelvalvet. Det här värdet kommer att användas under installationen av tjänsten i RCS och kallas *nyckelvalv-URI*.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]