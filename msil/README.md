# Patched MSIL/managed code DLLs

This folder contains managed code DLLs that have been manually patched to redirect or remove references to Win32 APIs that do not exist on Windows 95. They have been edited with [https://github.com/dnSpy/dnSpy](dnSpy).

.NET appears to use a hashing/signing system that will prevent these DLLs from getting installed into the Global Assembly Cache (GAC) by any normal means. Instead, the installer installs the original DLLs into the GAC and then clobbers them with these patched DLLs at the end. The hash/signing check is never done again so this ends up working, even though it is a hacky solution. There may be a better one I'm not aware of.
