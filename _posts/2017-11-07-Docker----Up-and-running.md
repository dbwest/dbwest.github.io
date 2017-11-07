---
layout: post
title: Docker -- Up and running... Windows and the Enterprise
---
Docker is generally easy to set up.

I'll focus on this post on something that may not be so straightforward: handling the practice common in some corporations involving a self-signed Enterprise certificate. 

The scenario I'm covering involves a Windows 7 computer on a network that requires such a certificate.

On Windows 7 you'll find that you need to run Docker from a Linux VM. Windows 10 is a different story, and doesn't involve this sort of 'shim' VM, but on Windows 7 you need a small Linux VM, AKA a `boot2docker` instance, also, perhaps confusingly called `default`.

If you are in such a situation, with the Enterprise CA certificate and all, you will likely find that you can't download from `https` sources which you'll likely need to rectify.

Doing so is simple. Simply put, your administrator installed the Enterprise certificate for Windows 7 for you so Windows 7 can handle `https`. Now you are making a new machine, inside your machine, and you need to put the certificate in the right place so it can use it when you pull down images and do other things.

There are a couple of good solutions I have found. One is from [a Stack Overflow post](https://www.google.com/url?sa=t&source=web&rct=j&url=https://stackoverflow.com/questions/31205438/docker-on-windows-boot2docker-certificate-signed-by-unknown-authority-error&ved=0ahUKEwiAnLfOzqzXAhWFQCYKHXGeBSEQjjgIJjAA&usg=AOvVaw0vcCs6fDsfwc47JaMDk7oL)