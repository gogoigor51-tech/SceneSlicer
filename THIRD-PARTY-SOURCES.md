# Сторонние компоненты / Third-party source materials

Установщик и переносной ZIP SceneSlicer содержат сторонние библиотеки. Их лицензии, copyright-уведомления и инструкции находятся в `licenses`. Соответствующие исходники опубликованы отдельными файлами в [выпуске1.2.2f](https://github.com/gogoigor51-tech/SceneSlicer/releases/tag/v1.2.2f): `SceneSlicer-1.2.2f-third-party-sources-*.zip`, индекс `third-party-source-index.json` и контрольные суммы `SHA256SUMS.txt`. Для использования программы скачивать исходники не нужно.

The installer and portable ZIP include third-party libraries. Their licenses, copyright notices and instructions are in `licenses`. Corresponding third-party sources are separate [release assets](https://github.com/gogoigor51-tech/SceneSlicer/releases/tag/v1.2.2f): `SceneSlicer-1.2.2f-third-party-sources-*.zip`, `third-party-source-index.json`, and `SHA256SUMS.txt`. Source archives are not needed to use the application.

| Component | Version / origin | Source/build information |
| --- | --- | --- |
| FFmpeg/FFprobe CLI | gyan.dev9.0.2 Essentials, GPLv3+ | Vendor dependency manifest, exact source revisions and MSYS2 source packages, full configure line. Vendor states no functional patches; follow each dependency's upstream build instructions. |
| FFmpeg multimedia DLLs | LGPL shared9.0,20261118, FFmpeg `d838f9f9ae` | Pinned FFmpeg-Builds recipes `7f2a6b1050d302144de8366afa37a75e46f326aa`, patches/dependency sources. Recipes match the successful [build run](https://github.com/FFmpeg-Builds/FFmpeg-Builds/actions/runs/44301161370). With Bash/Docker use `./makeimage.sh win64 lgpl-shared 9.0` and `./build.sh win64 lgpl-shared 9.0`; pin the FFmpeg checkout and dependency revisions to the included records rather than today's branch head. |
| Qt/PySide/Shiboken | 6.12.0, LGPLv3 | Official source archives with build documentation, bundled dependency notices. Follow Qt and PySide build documentation in those archives. |
| PyAV | 19.0.2, BSD | Source distribution plus public DLL-import relink script and change record. Only the verified LGPL DLL family is used for public playback. |
| RIFE/Real-ESRGAN ncnn Vulkan | MIT; model-specific licenses | Native tool sources, pinned ncnn/libwebp submodules and upstream notices. |
| Other bundled packages | See installed notices/source index | Upstream source licenses and additional notices; no SceneSlicer user data or credentials. |

## Замена LGPL-библиотек / Replacing LGPL libraries

Qt и FFmpeg DLL загружаются динамически из `_internal`. Можно заменить их совместимыми модифицированными сборками, сохраняя ABI и зависимости. Сделайте копию папки, замените соответствующие DLL и запустите `SceneSlicer.exe`. Проверки подписи обновлений защищают загрузку пакета, но не запрещают запуск с изменёнными LGPL-библиотеками. Обновление может заменить управляемые файлы: сохраняйте свои модификации отдельно. Обратная разработка для отладки таких изменений разрешена условиями LGPL.

Qt and FFmpeg DLLs load dynamically from `_internal`. You may replace them with compatible modified builds, preserving ABI and dependencies. Back up the folder, replace the relevant DLLs and launch `SceneSlicer.exe`. Update signatures protect downloaded packages; they do not prevent running modified LGPL libraries. Updates may replace managed files, so retain modifications separately. Reverse engineering needed to debug such modifications is permitted under the LGPL.

Исходники самого SceneSlicer пока не опубликованы. Условия приложения не ограничивают права, предоставленные лицензиями сторонних компонентов.

SceneSlicer application source is not published. Third-party license rights remain unchanged.
