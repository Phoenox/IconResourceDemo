cmake_minimum_required(VERSION 3.14)

project(IconResourceDemo VERSION 1.0.0.0 LANGUAGES CSharp)

include(CSharpUtilities)

add_executable(${PROJECT_NAME})

target_sources(${PROJECT_NAME}
    PRIVATE
    "App.config"
    "App.xaml"
    "App.xaml.cs"
    "MainWindow.xaml"
    "MainWindow.xaml.cs"

    "Properties/AssemblyInfo.cs"
    "Properties/Resources.Designer.cs"
    "Properties/Resources.resx"
    "Properties/Settings.Designer.cs"
    "Properties/Settings.settings"

    "Image_16x.png"
)

CSHARP_SET_DESIGNER_CS_PROPERTIES(
    "Properties/AssemblyInfo.cs"
    "Properties/Resources.Designer.cs"
    "Properties/Resources.resx"
    "Properties/Settings.Designer.cs"
    "Properties/Settings.settings"
)

CSHARP_SET_XAML_CS_PROPERTIES(
    "App.xaml"
    "App.xaml.cs"
    "MainWindow.xaml"
    "MainWindow.xaml.cs"
)

set_property(SOURCE App.xaml PROPERTY VS_XAML_TYPE "ApplicationDefinition")

set_target_properties(${PROJECT_NAME} PROPERTIES
    WIN32_EXECUTABLE TRUE
    VS_DOTNET_REFERENCES "System;System.Core;System.Data;System.Data.DataSetExtensions;System.Drawing;System.Net.Http;System.Xaml;System.Xml.Linq;Microsoft.CSharp;PresentationCore;PresentationFramework;WindowsBase"
    VS_GLOBAL_ROOTNAMESPACE ${PROJECT_NAME}
)
