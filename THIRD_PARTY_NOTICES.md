# 第三方组件与源码获取

FSAE Aero自身的软件许可不改变以下组件的许可。运行库按原形式动态分发，可在 `_internal` 中替换；为调试修改LGPL组件所必需的逆向工程不受软件许可限制。未将第三方组件重新许可为私有软件。

公开包不包含CATIA、WSL、OpenFOAM或Gmsh。这些外部软件由使用者单独安装并遵循各自条款。公开版STEP检查和轮轴识别采用OpenCASCADE/OCP。

| 组件 | 分发版本/来源 | 许可与源码 |
| --- | --- | --- |
| Python | 3.12.14 | PSF许可；[对应源码](https://www.python.org/ftp/python/3.12.14/Python-3.12.14.tar.xz) |
| Qt / PySide6 / Shiboken | 6.12.0 | 本包选择LGPLv3；[PySide/Shiboken源码](https://download.qt.io/official_releases/QtForPython/pyside6/PySide6-6.12.0-src/pyside-setup-everywhere-src-6.12.0.tar.xz)、[Qt源码](https://download.qt.io/official_releases/qt/6.12/6.12.0/submodules/) |
| OCP绑定 | cadquery-ocp 7.7.2 | Apache-2.0；[绑定源码](https://github.com/CadQuery/OCP)、[对应wheel构建系统](https://github.com/jmwright/ocp-build-system) |
| OpenCASCADE | 7.7.2，OCP原生依赖 | LGPL-2.1及OCCT例外；[对应源码](https://github.com/Open-Cascade-SAS/OCCT/tree/V7_7_2) |
| VTK | 9.7.1；OCP原生依赖另带9.2系列动态库 | BSD许可及附带第三方声明；[源码与发布](https://github.com/Kitware/VTK/releases) |
| NumPy / Matplotlib / Pillow / trimesh | 2.5.4 / 3.11.2 / 12.3.0 / 5.1.1 | 原许可全文及所含第三方声明见licenses中各包目录；[PyPI](https://pypi.org/)可按上述包名版本获得原始分发及来源 |
| pywin32、contourpy、cycler、fonttools、kiwisolver、packaging、pyparsing、python-dateutil、six | 与公开包运行库配套 | 原包许可见licenses对应目录；不将这些组件改作私有授权 |
| PyInstaller bootloader | 6.22.3 | GPL及bootloader分发例外，允许分发非GPL应用；全文见licenses/pyinstaller |
| FreeImage / LibRaw | OCP原生依赖 | 分别按FreeImage Public License及LGPL许可；全文见licenses/FreeImage.txt、LibRaw.txt及LGPL-2.1.txt；[FreeImage源码](https://freeimage.sourceforge.io/download.html)、[LibRaw源码](https://github.com/LibRaw/LibRaw) |
| FreeType、GLEW、OpenEXR/Imath、JPEG、LittleCMS、LERC、xz、PNG、WebP、OpenJPEG、pugixml、oneTBB、TIFF、zlib、zstd、libdeflate | OCP原生依赖 | 原项目的许可及版权声明分别放在licenses同名文本；源码入口见下表 |
| Microsoft Visual C++运行库 | Python/Qt/OCP动态依赖 | 按微软可再分发组件条款提供；[再分发说明](https://learn.microsoft.com/cpp/windows/redistributing-visual-cpp-files) |

## OCP原生依赖源码入口

以下源码由对应上游提供；没有修改这些库。分发中的动态库文件名和SHA256记录在下载包的MANIFEST.json，便于确认具体文件及替换后比较。

- [FreeType](https://gitlab.freedesktop.org/freetype/freetype)、[GLEW](https://github.com/nigels-com/glew)
- [OpenEXR](https://github.com/AcademySoftwareFoundation/openexr)、[Imath](https://github.com/AcademySoftwareFoundation/Imath)
- [libjpeg-turbo](https://github.com/libjpeg-turbo/libjpeg-turbo)、[LittleCMS](https://github.com/mm2/Little-CMS)、[LERC](https://github.com/Esri/lerc)
- [xz](https://github.com/tukaani-project/xz)、[PNG](https://github.com/pnggroup/libpng)、[WebP](https://github.com/webmproject/libwebp)
- [OpenJPEG](https://github.com/uclouvain/openjpeg)、[pugixml](https://github.com/zeux/pugixml)、[oneTBB](https://github.com/uxlfoundation/oneTBB)
- [TIFF](https://gitlab.com/libtiff/libtiff)、[zlib](https://github.com/madler/zlib)、[zstd](https://github.com/facebook/zstd)、[libdeflate](https://github.com/ebiggers/libdeflate)

许可正文包括LGPLv3、GPLv3（作为LGPLv3引用的正文）、LGPLv2.1、OCCT附加例外，以及各组件原有通知。源码链接和构建配方用于取得、修改并重建相应组件，不包含FSAE Aero私有开发历史。若链接失效或需要核对组件版本，请通过本仓库Issues提出；不要上传任何个人或车型数据。

其他随OCP原生wheel提供的依赖包括OpenSSL、curl、Expat、HDF4/HDF5、NetCDF、libssh2、LZ4、JSONcpp、double-conversion、SQLite、libiconv/libcharset、libzip、Ogg/Theora、PROJ、GL2PS、bzip2、SZIP与XDR；许可正文见licenses同名文件及VTK92通知。SZIP按其原始许可提供，不把其特定用途条款改写为无限制授权。
