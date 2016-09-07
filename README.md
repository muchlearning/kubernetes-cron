# Cron for Kubernetes

by MuchLearning

## Introduction

This container can be used to run periodic tasks in Kubernetes.

## Configuration

To add tasks to run, add a `/bin/sh` script to
`/etc/periodic/{15min|hourly|daily|weekly|monthly}`.  One way to do this in
Kubernetes is to mount a ConfigMap onto these directories.  The
[`cron.yaml`](https://github.com/muchlearning/kubernetes-cron/blob/master/cron.yaml)
file gives an example of doing this.  It creates 5 ConfigMaps, one for each of
the supported periods.

This container includes `kubectl`, which can be used to run commands in other
pods.  See the `cron-daily` ConfigMap for an example of using this.
