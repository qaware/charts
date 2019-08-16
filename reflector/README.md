# Reflector

The reflector automatically copies and synchronizes secrets and configmaps across multiple namespaces. 
Which secrets and which configmaps will be copied into which namespaces is controlled by labels.

## Secrets and ConfigMaps
Secrets and configmaps to be synchronized must be labeled with `reflector-class=<class>` where <class> is a (preferably short) custom string beginning and ending with an alphanumeric character and alphanumerics, dashes (-) and/or underscores (_) in between.

## Namespaces
Namespaces where secrets and configmaps should be copied/synchronized into must be labelled with `reflector-class=<class>[.<class>*]`, i.e. one or more classes separated by a dot.

### Example

A namespace labelled with `reflector-class=class1` will contain all secrets and configmaps labelled as `class1`.

A namespace labelled with `reflector-class=class1.class2.class3` will contain all secrets and configmaps labelled as `class1`, `class2` or `class3`.