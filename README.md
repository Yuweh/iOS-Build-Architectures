
## CPU Architectures


When building for the Cocoa platform, Elements allows you to choose to build for different CPU Architectures, depending on the target devices and operating system versions you wish to support. Elements allows the creation of so-called "Universal Binaries", or "Fat Binaries", that can include executable code for more than one platform (for example 32-bit and 64-bit).


You can pick one main set of architectures for your application, which might include one or more options depending on the SDK abd version. On iOS, tvOS and watchOS, in addition to picking architectures for the device deployment, you can also select separate architectures for running in the Simulator.



## macOS


On macOS, one architecture is supported as of now: 64-bit Intel, officially called x86_64 and sometimes also simply referred to as x64. Future versions of Elements and macOS might add support for additional platforms (for example if Apple releases ARM-based Macs).

Elements does not support the 32-bit i386 architecture for macOS, because the "Modern Objective-C Runtime", introduced with Mac OS X 10.5 Leopard, is not supported on 32-bit. The Modern Objective-C Runtime is a prerequisite for ARC, as well as many other runtime features Cocoa developers take for granted these days. Also, 32-bit Mac applications are largely irrelevant today, deprecated as of macOS 10.14 and totally unsupported as of macOS 10.15.


## iOS and iPadOS


On iOS and iPadOS, Elements supports three architectures for device deployment:

arm64 is the current 64-bit ARM CPU architecture, as used since the iPhone 5S and later (6, 6S, SE and 7), the iPad Air, Air 2 and Pro, with the A7 and later chips.
armv7s (a.k.a. Swift, not to be confused with the language of the same name), being used in Apple's A6 and A6X chips on iPhone 5, iPhone 5C and iPad 4.
armv7, an older variation of the 32-bit ARM CPU, as used in the A5 and earlier.
Very old iOS devices shipped before 2009 had armv6 CPUs, which are no longer supported by current iOS SDKs, nor by Elements.


In Project Settings, you can select to build your projects for one or more architectures. You can either choose architectures explicitly, or you can select Default, in which case no architectures will be hardcoded into the project settings, and the project will automatically be built against a default set of architectures (currently arm64-only). This is the most forward-thinking setting, since it will automatically include new architectures when you rebuild your project against newer SDKs.


arm64 is only available in iOS 7.0 or later.

armv7s is only available in iOS 6.0 or later.


Choose carefully when excluding architectures. An application build with armv7 will run on all current iOS devices, even those that support newer architectures (it will run as 32-bit on iPhone 5S and later). But on the other hand, an app build without armv7 will not run on older devices such as the iPhone 4/4S or the original iPad mini.


In addition to the device architecture, Project Settings will also let you choose architectures for the Simulators, where appropriate (i.e. on iOS).


x64_64 (i.e. 64-bit Intel) is optionally available starting with iOS 7.0.

i386 (i.e. 32-bit Intel) is the only option on iOS 6.1 and below.


Just as with the device architectures, a special Match Device option is provided for the Simulator Architectures. Selecting this option will once again not hardcode any architectures in the project; instead Elements will automatically pick the appropriate Simulator architectures, based on which device architectures you are building for. If your application includes armv7 and/or armv7s, it will include i386 in the Simulator architectures; if your are building for arm64 on the device, it will build for x86_64 on Simulator.


Just as on the device, Simulator builds can be Universal Binaries and include two (and potentially more, in the future) architectures. If built with both architectures, you can test your application in both 32-bit and 64-bit versions of the Simulator, without needing to rebuild.


## tvOS

On tvOS, Elements supports one architectures each for device deployment, and one for the Simulator:

arm64 is the current 64-bit ARM CPU architecture and used on Apple TV 4

x64_64 (i.e. 64-bit Intel) is used in the Simulator


## watchOS

On watchOS, Elements supports two architectures each for device deployment and for the Simulator

arm64_32 is a variant of arm64 with 32-bit pointer sizes, used on Apple Watch Series 4 and later.

armv7k is a 32-bit variant of regular armv7, and used from the orginal Apple Watch up to Series 3.

x86_64 (i.e. 64-bit Intel) is used in the Simulator

i386 (i.e. 32-bit Intel) is used in the Simulator


## UIKit for Mac


On UIKit for Mac, the same architecture(s) are supported as on macOS, currently only x86_64.


Source: https://docs.elementscompiler.com/Platforms/Cocoa/CpuArchitectures/



