# Fedora Linux에 설치

**Fedora 28 이상**에 대한 QOwnNotes저장소가 있습니다.

::: 팁 QOwnNotes는 [Fedora 리포지토리](https://packages.fedoraproject.org/pkgs/qownnotes/qownnotes/)에서 제공됩니다. 해당 버전은 일반적으로 마스터 리포지토리 뒤에 있는 하나 또는 두 개의 패치 버전입니다 아래 지침을 통해 사용할 수 있습니다.

대부분의 사용자의 경우 터미널 창에서 `dnf install qownnotes`을 발행할 수 있습니다. **최신 버전**을 원하신다면 계속 읽어주시기 바랍니다. :::

## Config-manager dnf 플러그인이 있는 시스템

다음 셸 명령을 root으로 실행하여 리포지토리를 추가합니다.

```bash
dnf config-manager --add-repo http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Fedora_\$releasever/

dnf makecache
dnf install qownnotes
```

::: 팁 레포키에서 다운로드하기 전에 레포키를 수락해야 할 수도 있습니다.

문제가 있는 경우 다음을 사용하여 키를 수동으로 가져옵니다:

```bash
rpm --import http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Fedora_40/repodata/repomd.xml.key
```

위 코드의 "Fedora_40" 부분은 사용 중인 Fedora 버전 (즉, "Fedora_39", "Fedora_38" 등)을 반영해야 합니다 :::

## 레거시 설치 방법

Fedora 버전이 `config-manager` dnf 플러그인을 지원하지 않는 경우 이 방법을 사용하여 다음 명령을 루트로 실행합니다.

다음 셸 명령을 root으로 실행하여 저장소를 신뢰합니다.

```bash
rpm --import http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Fedora_40/repodata/repomd.xml.key
```

다시: 위 코드의 "Fedora_40" 부분은 사용 중인 Fedora 버전 (즉, "Fedora_39", "Fedora_38" 등)을 반영해야 합니다

그런 다음 다음 다음 셸 명령을 root으로 실행하여 리포지토리를 추가하고 거기에서 QOwnNotes를 설치합니다.

```bash
cat > /etc/yum.repos.d/QOwnNotes.repo << EOL
[qownnotes]
name=OBS repo for QOwnNotes (Fedora \$releasever - \$basearch)
type=rpm-md
baseurl=http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Fedora_\$releasever/
gpgcheck=1
gpgkey=http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Fedora_\$releasever/repodata/repomd.xml.key
enabled=1
EOL

dnf clean expire-cache
dnf install qownnotes
```

[직접 다운로드](https://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Fedora_40) (이 예제 링크는 Fedora 40용)

## Fedora에 대한 QOwnNotes 버전 업데이트 참고 사항

### GPG 키에 문제가 있습니까?

Changes in Fedora's cryptographic policies can mean "old" (expired) repository keys are not _automatically_ extended. 이로 인해 _ 업데이트_ QOwnNotes 문제가 발생할 수 있습니다.

**세부 정보:** <0>인증서가 살아있지 않거나</0> 키 만료로 인해 키 만료로 인해 키가 `살아있지 않는` 등 잘못된 키 (예, GPG 오류) 에 문제가 있는 경우 이 터미널 명령은 만료된 키를 삭제해야 합니다:

```bash
sudo rpm -e $(rpm -q --qf "%{NAME}-%{VERSION}-%{RELEASE}\t%{SUMMARY}\n" gpg-pubkey | grep pbek | cut -f1)
```

명령에 대한 자세한 설명은 GitHub에서 이 정확한 문제와 관련된 [topic](https://github.com/pbek/QOwnNotes/issues/3008#issuecomment-2197827084) 에서 확인할 수 있습니다.

Once the expired key has been deleted, you must then newly _import_ the **current** key manually as described in the beginning of these installation instructions.
