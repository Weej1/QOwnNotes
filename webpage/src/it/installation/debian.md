# Installa su Debian Linux

## Debian Unstable

Eseguire i seguenti comandi della shell per considerare attendibile il repository.

```bash
SIGNED_BY='/etc/apt/keyrings/qownnotes.gpg'
sudo mkdir -p "$(dirname "${SIGNED_BY}")"
curl --silent --show-error --location http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_Unstable/Release.key | gpg --dearmor | sudo tee "${SIGNED_BY}" > /dev/null
sudo chmod u=rw,go=r "${SIGNED_BY}"
```

Eseguire i seguenti comandi della shell per aggiungere il repository e installare QOwnNotes da lì.

```bash
SIGNED_BY='/etc/apt/keyrings/qownnotes.gpg'
ARCHITECTURE="$(dpkg --print-architecture)"
echo "deb [arch=${ARCHITECTURE} signed-by=${SIGNED_BY}] http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_Unstable/ /" | sudo tee /etc/apt/sources.list.d/qownnotes.list > /dev/null
sudo apt update
sudo apt install qownnotes
```

::: tip
This package is built with Qt6.
:::

[Download diretto](https://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_Unstable)

## Debian 13.0

Eseguire i seguenti comandi della shell per considerare attendibile il repository.

```bash
SIGNED_BY='/etc/apt/keyrings/qownnotes.gpg'
sudo mkdir -p "$(dirname "${SIGNED_BY}")"
curl --silent --show-error --location http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_13/Release.key | gpg --dearmor | sudo tee "${SIGNED_BY}" > /dev/null
sudo chmod u=rw,go=r "${SIGNED_BY}"
```

Eseguire i seguenti comandi della shell per aggiungere il repository e installare QOwnNotes da lì.

```bash
SIGNED_BY='/etc/apt/keyrings/qownnotes.gpg'
ARCHITECTURE="$(dpkg --print-architecture)"
echo "deb [arch=${ARCHITECTURE} signed-by=${SIGNED_BY}] http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_13/ /" | sudo tee /etc/apt/sources.list.d/qownnotes.list > /dev/null
sudo apt update
sudo apt install qownnotes
```

::: tip
This package is built with Qt6.
:::

[Download diretto](https://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_13)

## Debian 12.0

Eseguire i seguenti comandi della shell per considerare attendibile il repository.

```bash
SIGNED_BY='/etc/apt/keyrings/qownnotes.gpg'
sudo mkdir -p "$(dirname "${SIGNED_BY}")"
curl --silent --show-error --location http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_12/Release.key | gpg --dearmor | sudo tee "${SIGNED_BY}" > /dev/null
sudo chmod u=rw,go=r "${SIGNED_BY}"
```

Eseguire i seguenti comandi della shell per aggiungere il repository e installare QOwnNotes da lì.

```bash
SIGNED_BY='/etc/apt/keyrings/qownnotes.gpg'
ARCHITECTURE="$(dpkg --print-architecture)"
echo "deb [arch=${ARCHITECTURE} signed-by=${SIGNED_BY}] http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_12/ /" | sudo tee /etc/apt/sources.list.d/qownnotes.list > /dev/null
sudo apt update
sudo apt install qownnotes
```

::: tip
This package is built with Qt6.
:::

[Download diretto](https://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_12)

## Debian 11.0

Eseguire i seguenti comandi della shell per considerare attendibile il repository.

```bash
SIGNED_BY='/etc/apt/keyrings/qownnotes.gpg'
sudo mkdir -p "$(dirname "${SIGNED_BY}")"
curl --silent --show-error --location http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_11/Release.key | gpg --dearmor | sudo tee "${SIGNED_BY}" > /dev/null
sudo chmod u=rw,go=r "${SIGNED_BY}"
```

Eseguire i seguenti comandi della shell per aggiungere il repository e installare QOwnNotes direttamente da essa.

```bash
SIGNED_BY='/etc/apt/keyrings/qownnotes.gpg'
ARCHITECTURE="$(dpkg --print-architecture)"
echo "deb [arch=${ARCHITECTURE} signed-by=${SIGNED_BY}] http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_11/ /" | sudo tee /etc/apt/sources.list.d/qownnotes.list > /dev/null
sudo apt update
sudo apt install qownnotes
```

::: tip
Se usi questa repository per altre versioni Linux di Debian verifica di avere **Qt** installato almeno alla versione **5.11**.
:::

[Download diretto](https://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_11)

## Debian 10.0

Run the following shell commands to trust the repository.

```bash
wget http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_10/Release.key -O - | sudo apt-key add -
```

Run the following shell commands to add the repository and install QOwnNotes from there.

```bash
sudo bash -c "echo 'deb http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_10/ /' >> /etc/apt/sources.list.d/qownnotes.list"
sudo apt-get update
sudo apt-get install qownnotes
```

::: tip
Se usi questa repository per altre versioni Linux di Debian verifica di avere **Qt** installato almeno alla versione **5.8**.
:::

[Direct Download](https://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_10)

## Debian 9.0

Run the following shell commands to trust the repository.

```bash
wget http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_9.0/Release.key -O - | sudo apt-key add -
```

Run the following shell commands to add the repository and install QOwnNotes from there.

```bash
sudo bash -c "echo 'deb http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_9.0/ /' >> /etc/apt/sources.list.d/qownnotes.list"
sudo apt-get update
sudo apt-get install qownnotes
```

::: tip
Se usi questa repository per altre versioni Linux di Debian verifica di avere **Qt** installato almeno alla versione **5.5**.
:::

[Direct Download](https://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Debian_9.0)
