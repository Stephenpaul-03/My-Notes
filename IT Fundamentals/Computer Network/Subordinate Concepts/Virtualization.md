## **Virtualization**

- **Virtualization** in the context of operating systems is a foundational technology that allows one physical machine to run multiple **isolated virtual environments -** such as virtual machines (VMs) or containers - on the same hardware, optimizing resource usage, flexibility, and scalability.

## **Key Concepts**

- **Virtualization** is the creation of a *virtual* (rather than physical) version of computing resources, often servers, operating systems, storage devices, or network resources.
- The main goal is to enable better utilization of physical hardware by allowing multiple software environments to run independently and securely.

## **Types of Virtualization**

| Type | Description | Example |
| --- | --- | --- |
| **Full Virtualization** | Each VM runs its own separate OS instance on top of a hypervisor; hardware fully abstracted | VMware, VirtualBox, KVM |
| **OS-level Virtualization** | Multiple *isolated user-space instances* (containers) run on a single OS kernel; kernel is shared | Docker, LXC, FreeBSD Jails |

## **How Virtualization Works**

- **Hypervisor**:
    - A core component enabling virtualization; it acts as an abstraction layer between the hardware and OS.
    - Two main kinds:
        - **Type 1 (Bare-metal)**: Runs directly on hardware, manages guest OSs without a host OS (e.g., VMware ESXi, Microsoft Hyper-V).
        - **Type 2 (Hosted)**: Runs as an application atop a host OS (e.g., VirtualBox, VMware Workstation).
- **Virtual Machines (VMs)**:
    - Software emulations of physical machines, with virtualized CPU, memory, disk, and network interfaces.
    - Each VM can have its own OS and applications, isolated from others.
- **Containers / OS-level Virtualization**:
    - The OS kernel enables multiple containers , isolated user-space environments - sharing the same kernel but with separate processes and resources.
    - Linux uses **namespaces** (for isolation) and **cgroups** (for resource control) to enforce container boundaries and resource usage.

## **Benefits of OS Virtualization**

- **Efficient Resource Utilization**: Maximizes use of CPU, memory, and storage across many workloads.
- **Isolation**: Each VM or container runs in its own space; one cannot interfere with another, enhancing security and reliability.
- **Flexibility**: Multiple OSs (Windows, MacOS, Linux, etc.) or different app environments can run on a single hardware system.
- **Portability**: Virtual environments can be moved, cloned, or backed up easily.
- **Scalability and Rapid Deployment**: VMs and containers can be deployed, duplicated, or removed quickly to respond to workload changes.

## **Drawbacks**

- **Overhead**: Some system resources are needed to manage virtualization, which can slightly reduce raw performance compared to running directly on hardware, although containers have minimal overhead compared to full VMs.
- **Compatibility**: Not all OSs or applications are compatible with all virtualization platforms or hypervisors.

## **Common Use Cases**

- Testing different OS and app configurations on a single device.
- Running legacy OSs or apps alongside modern systems.
- Isolating and sandboxing potentially unsafe applications.
- Cloud hosting providers offering scalable, multi-tenant environments.