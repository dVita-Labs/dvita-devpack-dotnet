##
## Copyright (c) 2021 - Team11. All rights reserved.
##

all: build

build: restore
	dotnet publish -c Release -o ./dist

restore:
	dotnet restore

test:
	dotnet test

align-project: Neo.Compiler.CSharp.csproj
	dotnet remove $< reference Neo
	dotnet add $< reference ../../../neo/src/neo/neo.csproj

clean:
	-@dotnet clean 2>&1 > /dev/null
	-@rm -rf ./dist
	-@rm -rf ./bin
	-@rm -rf ./obj
	-@rm -rf ../Neo.Compiler.CSharp/bin
	-@rm -rf ../Neo.Compiler.CSharp/obj
	-@rm -rf ../tests/Neo.Compiler.CSharp.Tests/obj

.PHONY: all build restore test align-project clean

.SILENT: clean
