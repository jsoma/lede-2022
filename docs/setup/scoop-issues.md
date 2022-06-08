# Scoop issue fix

## Scoop error on package install: Convert-RepositoryUri

Some people have been getting a `Convert-RepositoryUri` error when installing with Scoop, it looks like this:

```
λ scoop install wget
Updating Scoop...
Updating 'main' bucket...
 Converting 'main' bucket to git...
0
Convert-RepositoryUri : Cannot bind argument to parameter 'Uri' because it is an empty string.
At C:\Users\Gabriela\scoop\apps\scoop\current\lib\buckets.ps1:159 char:44
+     $uni_repo = Convert-RepositoryUri -Uri $repo
+                                            ~~~~~
    + CategoryInfo          : InvalidData: (:) [Convert-RepositoryUri], ParameterBindingValidationException
    + FullyQualifiedErrorId : ParameterArgumentValidationErrorEmptyStringNotAllowed,Convert-RepositoryUri
1
Scoop was updated successfully!
Couldn't find manifest for 'wget'.
```

This is  [because Scoop is broken at the moment](https://github.com/ScoopInstaller/Scoop/issues/4917), so it should go away soon, but there's another solution that seems to work, too. Run each of these commands below, one at a time:

First we'll remove the bucket called "main" (a bucket is a... list of things that can be installed, I think?)

```shell
scoop bucket rm main
```

and then we'll add it back, since it seems to be broken but maybe adding it back works

```shell
scoop bucket add main
```

and then install a couple tools we need

```shell
scoop install 7zip git openssh
```

and then see if installing wget works

```shell
scoop install wget
```