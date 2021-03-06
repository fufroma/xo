# ACLs

ACLs are the permissions for your users or groups. The ACLs view can be accessed in the "Settings".

1. Select the user or group you want to apply permissions on it
2. Select the object on which the permission will apply
3. Choose the role for this ACL
4. Click on "Create"

![](./assets/createacl.png)

> Pro tip: you can click to add multiple objects at the same time!

Your ACL is now available in the right list:

![](./assets/acllist.png)

You can edit/remove existing ACLs here.

## Roles

There is 3 different roles for your users:

* Admin
* Operator
* Viewer

### Admin

An object admin can do everything on it, even destroy it. E.g with its admin VM:

* create a new VM
* remove it
* migrate it (to a host with admin permission on it)
* modify the VM resources, name and description
* clone it
* copy it
* convert it into a template
* snapshot it (even revert from a snapshot)
* export it
* attach/add visible disks
* same for network cards

### Operator

An operator can make everyday operations on assigned objects. E.g on a VM:

* eject a CD
* insert a CD (if he can view the ISO storage repository)
* start, restart, shutdown, suspend/resume it

All other operations are forbidden.

### Viewer

A viewer can only access the object console (if any) and see the object metrics. That's all!

## Inheritance

Objects have a hierarchy: a Pool contains all its hosts, containing itself all its VMs.

If you give a *view* permission to a user (or a group) on a pool, he will automatically see all the objects inside this pool (SRs, hosts, VMs).

## Examples

### Allow a user to install an OS

If the OS install needs a ISO, you need to give this user 2 permissions:

* *Operate* on the VM (e.g to start it)
* *View* on the ISO Storage containing the needed ISO.

### Console only

If you want to give your user access to the VM console only, the *View* permission is enough.
