# Installation

## Basic Installation

You can load **ToDo Application** evaluating:
```smalltalk
Metacello new
	baseline: 'ToDo';
	repository: 'github://fortizpenaloza/ToDo:master/source';
	load.
```
>  Change `master` to some released version if you want a pinned version

## Using as dependency

In order to include **ToDo Application** as part of your project, you should reference the package in your product baseline:

```smalltalk
setUpDependencies: spec

	spec
		baseline: 'ToDo'
			with: [ spec
				repository: 'github://fortizpenaloza/ToDo:v{XX}/source';
				loads: #('Deployment') ];
		import: 'ToDo'.
```
> Replace `{XX}` with the version you want to depend on

```smalltalk
baseline: spec

	<baseline>
	spec
		for: #common
		do: [ self setUpDependencies: spec.
			spec package: 'My-Package' with: [ spec requires: #('ToDo') ] ]
```
