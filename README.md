# Arkeon güven paketi / Arkeon trust bundle

Bu depo yalnız Arkeon'un imzalı güven paketini dağıtır. Kaynak kod içermez.

Her sürümün Release'inde iki dosya bulunur:

- `arkeon-trust-bundle.json`: Arkeon'un e-imza, e-mühür ve zaman damgası doğrulamasında kullandığı güvenilir kök sertifikaların imzalı listesi (BTK listesindeki ESHS kökleri)
- `arkeon-trust-bundle.json.sha256`: paketin SHA-256 özeti

Arkeon kurulumları paketi şu sabit adresten indirir:

```
https://github.com/appouse/arkeon-trust/releases/latest/download/arkeon-trust-bundle.json
```

Arkeon paketi yalnız uygulamaya gömülü (sabitlenmiş) genel anahtarlarla doğrulanan imza geçerliyse kabul eder. Paket uygulanmadan önce platform yöneticisinin onayını bekler. Bu nedenle paketin nereden indirildiği güvenliği etkilemez.

İnternet erişimi olmayan kurulumlar için paket ve `.sha256` dosyası Release sayfasından indirilip **Platform › Güvenilir kökler › Paket içe aktar** ile yüklenebilir. İndirilen dosyanın bütünlüğünü denetlemek için:

```bash
sha256sum -c arkeon-trust-bundle.json.sha256
```

---

This repository only distributes Arkeon's signed trust bundle (no source code). Arkeon accepts a bundle only when its signature verifies against the public keys pinned in the application, and the platform owner approves it before it is applied. Offline installs can download the bundle and its `.sha256` file from the Releases page and import them on the platform trust store screen.
