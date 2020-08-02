# YAML - Yet Another Markup Languange

YAML files consists of maps and lists
Indentation matters and has to be consistent. Always use spaces
Maps are key value pairs:
    - name: value pairs
    - Maps can contain other maps for more complext data structures
Lists:
    - Sequence of items
    - Multiple maps can be defined in a list

![YAML](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/YAML.JPG)

![YAML Specifications](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/YAMLSpecifications.JPG)

Post creating the YAML file, we can run the following command to create POD and to validate the YAML file
**kubectl create -f [name of the YAML file] --dry-run --validate=true**

Post validation to create a POD from YAML file
**kubectl create -f [name of the YAML file]**

Use Save config file when you want to use kubectl apply in future. Save config store current properties in resources annotation
**kubectl create -f [name of the YAML file] --save-config**

Alternative way to create or apply changes to a pod with YAML
**kubectl apply -f [name of the YAML file]**

To delete pod when created using YAML
**kubectl delete pod -f [name of the YAML file]**