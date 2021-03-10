# Cake.SonarScanner

## Pre requisites
Ensure [sonar-scanner](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner) is on your path
Suggestion: use chocolatey. https://chocolatey.org/packages/sonarqube-scanner.portable

## Usage
```cs
#tool "choco:?package=sonarcube-scanner&version=3.0.3.778&include=./**/*.bat"
#addin "nuget:?package=Cake.SonarScanner"
    
// Assuming a sonar-scanner.properties on the current directory
SonarScanner(new SonarScannerSettings {
    Properties = new Dictionary<string, string> {
        {"sonar.login", EnvironmentVariable("sonar_scanner_token")}
    }
});
```

## Important
.net projects should use the MSBuild scanner for SonarQube. See https://github.com/AgileArchitect/Cake.Sonar

[![Build status](https://ci.appveyor.com/api/projects/status/l00o9jw5cxh68255?svg=true)](https://ci.appveyor.com/project/pitermarx/cake-sonarscanner)
[![NuGet](https://img.shields.io/nuget/v/Cake.SonarScanner.svg)](https://www.nuget.org/packages/Cake.SonarScanner/)
[![Coverage Status](https://coveralls.io/repos/github/pitermarx/Cake.SonarScanner/badge.svg?branch=master)](https://coveralls.io/github/pitermarx/Cake.SonarScanner?branch=master)
[![Quality Gate](https://sonarcloud.io/api/project_badges/measure?project=pitermarx%3ACake.SonarScanner&metric=alert_status)](https://sonarcloud.io/dashboard/index/pitermarx:Cake.SonarScanner)
