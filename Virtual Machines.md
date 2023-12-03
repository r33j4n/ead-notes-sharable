#VM #AzureVM 
## What is a virtual machine?

> A Virtual Machine (VM) is a software-based emulation of a physical computer. It allows you to run an operating system (OS) and associated applications on a virtualized environment, which is created and managed by a hypervisor or a virtual machine monitor (VMM). The key features of virtual machines include isolation, encapsulation, and the ability to run multiple VMs on a single physical machine.

Here are the main components and concepts associated with virtual machines:

1. **Hypervisor:**
   - *Definition:* A hypervisor, also known as a Virtual Machine Monitor (VMM), is software or firmware that creates and manages virtual machines. It abstracts the underlying hardware and allocates resources to different VMs.

   - *Types:* There are two main types of hypervisors:
     - **Type 1 (Bare Metal):** Runs directly on the hardware without the need for a host operating system. Examples include VMware ESXi, Microsoft Hyper-V Server, and Xen.
     - **Type 2 (Hosted):** Runs on top of a host operating system and relies on the host OS for resource management. Examples include VMware Workstation, Oracle VirtualBox, and Microsoft Hyper-V (when installed on Windows).

2. **Virtual Machine (VM):**
   - *Definition:* A virtual machine is a complete and independent software-based representation of a physical computer. It includes its own virtual CPU, memory, storage, and network interfaces.

   - *Isolation:* Each VM is isolated from the others, allowing multiple operating systems to run on the same physical hardware without interference.

3. **Guest OS:**
   - *Definition:* The guest operating system is the operating system running inside a virtual machine. It can be different from the host operating system.

   - *Example:* Running a Linux VM on a host machine that has a Windows operating system.

4. **Host OS:**
   - *Definition:* The host operating system is the operating system installed directly on the physical hardware or, in the case of Type 2 hypervisors, on top of which the hypervisor runs.

   - *Example:* Windows or Linux operating system running directly on the physical hardware or serving as a host for virtualization.

5. **Snapshot:**
   - *Definition:* A snapshot is a point-in-time image of a virtual machine. It captures the VM's current state, including the operating system, applications, and data.

   - *Use Case:* Creating a snapshot before making changes to a VM allows for easy rollback if the changes cause issues.

6. **Resource Allocation:**
   - *Definition:* Hypervisors allocate physical resources such as CPU, memory, storage, and network bandwidth to each virtual machine.

   - *Dynamic Allocation:* Resources can be dynamically adjusted based on the demands of each VM.

Virtual machines are widely used in various scenarios, including server virtualization, development and testing environments, and desktop virtualization. They provide flexibility, efficient resource utilization, and the ability to create and manage complex computing environments.

## Key Characteristics of VM

> The key characteristics of virtual machines (VMs) include features and attributes that distinguish them from physical machines. These characteristics contribute to the flexibility, efficiency, and isolation provided by virtualization technologies. Here are the main key characteristics of virtual machines:

1. **Isolation:**
   - *Description:* VMs are isolated instances that operate independently of each other. Each VM has its own virtualized hardware resources, ensuring that actions or issues in one VM do not affect others.

2. **Encapsulation:**
   - *Description:* VMs encapsulate an entire computing environment, including the operating system, applications, and data. This encapsulation allows for easy movement, replication, and management of VMs across different physical hosts.

3. **Hardware Independence:**
   - *Description:* VMs are hardware-independent, meaning they can run on different physical machines with varying hardware configurations. This provides flexibility in deploying and migrating VMs across diverse environments.

4. **Resource Allocation and Dynamic Adjustment:**
   - *Description:* Hypervisors dynamically allocate physical resources, such as CPU, memory, storage, and network bandwidth, to VMs. Resources can be adjusted based on the demands of each VM, allowing for efficient utilization.

5. **Snapshot and Rollback:**
   - *Description:* VMs support the creation of snapshots, which are point-in-time images capturing the VM's state. Snapshots enable users to roll back to a specific configuration if changes or updates lead to issues.

6. **Multiple Operating Systems:**
   - *Description:* VMs allow running multiple operating systems on the same physical hardware. This is particularly useful for testing applications across different OS environments or running legacy software.

7. **Ease of Deployment:**
   - *Description:* VMs can be deployed rapidly compared to physical machines. Virtualization technologies enable the quick creation and provisioning of VMs, streamlining the deployment process.

8. **Consolidation:**
   - *Description:* Multiple VMs can run on a single physical server, leading to server consolidation. This consolidation improves resource utilization and reduces the need for extensive hardware infrastructure.

9. **Migration and Mobility:**
   - *Description:* VMs can be easily moved or migrated between different physical hosts without significant downtime. This feature facilitates workload balancing, maintenance, and disaster recovery.

10. **Security Isolation:**
    - *Description:* VMs provide a level of security isolation, limiting the impact of security breaches or vulnerabilities in one VM on others. Security measures can be implemented at the hypervisor level to enhance overall system security.

11. **Cloning and Template Creation:**
    - *Description:* VMs can be cloned or used as templates to create new instances with similar configurations. This accelerates the provisioning of identical VMs for specific use cases.

12. **Virtual Networking:**
    - *Description:* VMs have virtual network interfaces, allowing them to communicate with each other and with external networks. Virtual networking configurations are flexible and can be adjusted to suit different requirements.

Understanding these key characteristics is essential for effectively leveraging virtualization technologies in various computing environments, from data centers to desktops. Virtual machines play a crucial role in achieving resource efficiency, scalability, and flexibility in modern IT infrastructures.

## Why we use VMs ?

> Virtual machines (VMs) are widely used in computing environments for various reasons, providing several benefits and addressing specific challenges. Here are the key reasons why virtual machines are commonly used:

1. **Resource Efficiency:**
   - *Explanation:* VMs allow multiple virtualized instances to run on a single physical server. This consolidation improves resource utilization, reducing the need for extensive hardware infrastructure.

2. **Server Consolidation:**
   - *Explanation:* Virtualization enables the consolidation of multiple servers or workloads onto a smaller number of physical machines. This consolidation results in better overall resource utilization and cost savings.

3. **Isolation and Security:**
   - *Explanation:* VMs operate in isolated environments, ensuring that issues in one VM do not impact others. This isolation enhances security by containing potential vulnerabilities or breaches within individual virtualized instances.

4. **Flexibility and Scalability:**
   - *Explanation:* VMs provide flexibility in deploying and scaling applications. They can be quickly provisioned, duplicated, and moved across different physical hosts, facilitating scalability and adaptability to changing workloads.

5. **Testing and Development:**
   - *Explanation:* VMs are valuable for testing and development environments. Developers can create isolated instances with specific configurations, and testing scenarios without affecting the production environment.

6. **Legacy Application Support:**
   - *Explanation:* VMs enable running legacy applications on modern hardware. This is particularly useful when older software is incompatible with current operating systems or hardware.

7. **Rapid Deployment:**
   - *Explanation:* VM templates and snapshots allow for the rapid deployment of standardized configurations. This accelerates the provisioning process for new instances, reducing setup time.

8. **Disaster Recovery:**
   - *Explanation:* VMs support snapshotting and replication, making it easier to implement disaster recovery strategies. In the event of a system failure, VMs can be quickly restored to a known state.

9. **Consistent Development Environments:**
   - *Explanation:* VMs provide a consistent environment across different development stages. Developers can work in identical VM setups, reducing issues related to environmental inconsistencies.

10. **Energy Efficiency:**
    - *Explanation:* Server consolidation through virtualization contributes to energy efficiency. Running fewer physical servers with higher utilization can result in lower power consumption.

11. **Compatibility and Cross-Platform Development:**
    - *Explanation:* VMs enable running different operating systems on the same physical hardware. This is beneficial for cross-platform development, testing, and ensuring compatibility across diverse environments.

12. **Optimized Utilization of High-Performance Hardware:**
    - *Explanation:* VMs can leverage high-performance hardware features. For example, a powerful server with multiple CPUs and large amounts of RAM can host multiple VMs, each with a designated share of resources.

13. **Cost Savings:**
    - *Explanation:* VMs contribute to cost savings by reducing the number of physical servers required, minimizing hardware costs, and improving overall operational efficiency.

In summary, the use of virtual machines offers a flexible and efficient approach to managing computing resources, addressing challenges related to resource utilization, scalability, security, and development environments in various IT scenarios.

# Virtual Machine Proper Definition
---
  
### A virtual machine is a virtual representation, or emulation, of a physical computer. They are often referred to as a guest while the physical machine they run on is referred to as the host.


> [Virtualization](https://www.ibm.com/topics/virtualization) makes it possible to create multiple virtual machines, each with their own operating system (OS) and applications, on a single physical machine. **A VM cannot interact directly with a physical computer**. Instead, it needs a lightweight software layer called a [hypervisor](https://www.ibm.com/topics/hypervisors) to coordinate between it and the underlying physical hardware. **The hypervisor allocates physical computing resources—such as processors, memory, and storage—to each VM.** It keeps each VM separate from others so they don’t interfere with each other.

While this technology can go by many names, including virtual server, virtual server instance (VSI) and virtual private server (VPS), this article will simply refer to them as virtual machines.

## How virtualization works

When a hypervisor is used on a physical computer or server, (also known as bare metal server), it allows the physical computer to separate its operating system and applications from its hardware. Then, it can divide itself into several independent “virtual machines.”

Each of these new virtual machines can then run their own operating systems and applications independently while still sharing the original resources from the bare metal server, which the hypervisor manages. Those resources include memory, RAM, storage, etc.

The hypervisor acts like a traffic cop of sorts, directing and allocating the bare metal’s resources to each of the various new virtual machines, ensuring they don’t disrupt each other.

There are two primary types of hypervisors.

**Type 1 hypervisors** run directly on the physical hardware (usually a server), taking the place of the OS. Typically, you use a separate software product to create and manipulate VMs on the hypervisor. Some management tools, like VMware’s vSphere, let you select a guest OS to install in the VM.

You can use one VM as a template for others, duplicating it to create new ones. Depending on your needs, you might create multiple VM templates for different purposes, such as software testing, production databases, and development environments.

**Type 2 hypervisors** run as an application within a host OS and usually target single-user desktop or notebook platforms. With a Type 2 hypervisor, you manually create a VM and then install a guest OS in it. You can use the hypervisor to allocate physical resources to your VM, manually setting the amount of processor cores and memory it can use. Depending on the hypervisor’s capabilities, you can also set options like 3D acceleration for graphics.

The following video explains the basics of virtualization. Also check out the article, "[5 Benefits of Virtualization](https://www.ibm.com/blog/5-benefits-of-virtualization/)."

![Virtualization Explained](https://cdnsecakmi.kaltura.com/p/1773841/thumbnail/entry_id/1_d8gcrfl3/width/640)

Virtualization Explained (5:19)

Advantages of VMs

VMs offer several benefits over traditional physical hardware:

- **Resource utilization and improved ROI**: Because multiple VMs run on a single physical computer, customers don’t have to buy a new server every time they want to run another OS, and they can get more return from each piece of hardware they already own.  
      
    
- **Scale**: With [cloud computing](https://www.ibm.com/topics/cloud-computing), it’s easy to deploy multiple copies of the same virtual machine to better serve increases in load.  
      
    
- **Portability**: VMs can be relocated as needed among the physical computers in a network. This makes it possible to allocate workloads to servers that have spare computing power. VMs can even move between on-premises and cloud environments, making them useful for [hybrid cloud](https://www.ibm.com/topics/hybrid-cloud) scenarios in which you share computing resources between your data center and a cloud service provider.  
      
    
- **Flexibility**: Creating a VM is faster and easier than installing an OS on a physical server because you can clone a VM with the OS already installed. Developers and software testers can create new environments on demand to handle new tasks as they arise.  
      
    
- **Security**: VMs improve security in several ways when compared to operating systems running directly on hardware. A VM is a file that can be scanned for malicious software by an external program. You can create an entire snapshot of the VM at any point in time and then restore it to that state if it becomes infected with malware, effectively taking the VM back in time. The fast, easy creation of VMs also makes it possible to completely delete a compromised VM and then recreate it quickly, hastening recovery from malware infections.

## VM use cases

VMs have several uses, both for enterprise IT administrators and users.

**Cloud computing:** For the last 10+ years, VMs have been the fundamental unit of compute in cloud, enabling dozens of different types of applications and workloads to run and scale successfully.

**Supporting [DevOps](https://www.ibm.com/topics/devops)**: VMs are a great way to support enterprise developers, who can configure VM templates with the settings for their software development and testing processes. They can create VMs for specific tasks such as static software tests, including these steps in an automated development workflow. This all helps streamline the DevOps toolchain.

**Testing a new operating system**: A VM lets you test-drive a new operating system on your desktop without affecting your primary OS.

**Investigate malware**: VMs are useful for malware researchers that frequently need fresh machines on which to test malicious programs.

**Running incompatible software**: Some users may prefer one OS while still needing a program that is only available in another. One good example is the Dragon range of voice dictation software. Its vendor, Nuance, has discontinued the macOS version of its product. However, running a desktop-focused hypervisor—such as VMware Fusion or Parallels—enables you to run Windows in a VM, giving you access to that version of the software.

**Browsing securely**: Using a virtual machine for browsing enables you to visit sites without worrying about infection. You can take a snapshot of your machine and then roll back to it after each browsing session. This is something that a user could set up themselves, using a Type 2 desktop hypervisor. Alternatively, an admin could provide a temporary virtual desktop located on the server.

Types of VMs

### Windows virtual machines

Most hypervisors support VMs running the Windows OS as a guest. Microsoft’s Hyper-V hypervisor comes as part of the Windows operating system. When installed, it creates a parent partition containing both itself and the primary Windows OS, each of which gets privileged access to the hardware. Other operating systems, including Windows guests, run in child partitions that communicate with the hardware via the parent partition.

### Android virtual machines

Google’s open-source [Android OS](https://www.ibm.com/topics/android-development) is common on mobile devices and connected home devices such as home entertainment devices. The Android OS runs only on the ARM processor architecture that is common to these devices, but enthusiasts, Android gamers, or software developers might want to run it on PCs.

This is problematic because PCs run on an entirely different x86 processor architecture and a hardware virtualization hypervisor only passes instructions between the VM and the CPU. It doesn’t translate them for processors with different instruction sets. There are various projects to address this problem.

Some projects, such as Shashlik or Genymotion, use an emulator that re-creates the ARM architecture in software. One alternative, the Android-x86 project, ports Android to the x86 architecture instead. To run it, you must install the Android-x86 program as a virtual machine using the VirtualBox type 2 hypervisor. Another alternative, Anbox, runs the Android operating system on the kernel of a host Linux OS.

### Mac virtual machines

Apple only allows its macOS system to run on Apple hardware, prohibiting people from running it on non-Apple hardware as a VM or otherwise under its end user license agreement. You can use Type 2 hypervisors on Mac hardware to create VMs with a macOS guest.

### iOS virtual machines

It is not possible to run iOS in a VM today because Apple strictly controls its iOS OS and doesn’t allow it to run on anything other than iOS devices.

The closest thing to an iOS VM is the iPhone simulator that ships with the Xcode integrated development environment, which simulates the entire iPhone system in software.

### Java virtual machines

The Java platform is an execution environment for programs written in the Java software development language. Java’s promise was “write once, run anywhere” functionality. This meant that any Java program could run on any hardware running the Java platform. To achieve that, the Java platform includes a Java virtual machine (JVM).

Java programs contain bytecode, which are instructions intended for the JVM. The JVM compiles this bytecode to machine code, which is the lowest-level language used by the host computer. The JVM in one computing platform’s Java platform will create a different set of machine code instructions to the JVM in another’s, based on the machine code that the processor expects.

The JVM, therefore, doesn’t run an entire OS and doesn’t use a hypervisor as other VMs do. Instead, it translates application-level software programs to run on particular hardware.

For more information on Java, check out “[Java: A Complete Guide](https://www.ibm.com/topics/java).”

### Python virtual machines

Like the JVM, the Python VM doesn’t run on a hypervisor, and it doesn’t contain a guest OS. It is a tool that enables programs written in the Python programming language to run on a variety of CPUs.

Similar to Java, Python translates its programs into an intermediate format called bytecode, storing it in a file ready for execution. When the program runs, the Python VM translates the bytecode into machine code for fast execution.

### Linux virtual machines

Linux is a common guest OS used in many VMs. It is also a common host OS used to run VMs and even has its own hypervisor called the kernel-based virtual machine (KVM). The mainstream Linux kernel has included the KVM since 2007. Although it is an open source project, Red Hat now owns the original company that developed the KVM.

### VMware virtual machines

VMware was an early virtualization software vendor and is now a popular provider of both Type 1 and Type 2 hypervisor and VM software to enterprise customers.

“[VMware: A Complete Guide](https://www.ibm.com/topics/vmware)” provides a comprehensive overview of all things VMware.

### Ubuntu virtual machines

Ubuntu is a Linux distribution produced by Canonical. It is available in desktop and server versions, either of which you can install as a VM. Ubuntu can be deployed as a guest OS on Microsoft Hyper-V. It provides an optimized version of Ubuntu Desktop that works well in Hyper-V’s Enhanced Session Mode, providing tight integration between the Windows host and Ubuntu VM. It includes support for clipboard integration, dynamic desktop resizing, shared folders, and moving the mouse between the host and guest desktops.

### Multi-tenant vs. single-tenant

In cloud computing, virtual machines are typically offered in both single-tenant and multi-tenant variations.

Public, or multi-tenant, virtual machines are virtual machines in which multiple users are sharing common physical infrastructure. This is most cost effective and scalable approach to provisioning virtual machines, but lacks some of isolation characteristics that organizations with strict security or compliance mandates might prefer.

Two models for single-tenant virtual machines are dedicated hosts and dedicated instances.

A _dedicated host_ involves renting an entire physical machine and maintaining sustained access to and control over that machine, its hardware, and whatever software is installed on it. This model provides the maximum amount of hardware flexibility and transparency, workload control and placement, and also offers some advantages for certain bring-your-own license software.

A _dedicated instance_ offers the same single-tenant isolation and the same control over workload placement, but it is not coupled with a specific physical machine. So, for example, if a dedicated instance is re-booted, it could wind up on a new physical machine—a machine dedicated to the individual account, but nonetheless a new machine, potentially in a different physical location.

### Pricing models for VMs

The most common pricing models for virtual machines in the cloud are pay-as-you-go (by the hour or second), transient/spot instances, reserved instances and dedicated hosts.

- **Pay-as-you-go**: In the pay-as-you-go model, there are no upfront costs for the virtual machine and users simply pay for what they use, typically billed by the hour or second depending on the provider and instance type.  
      
    
- **Transient/spot instances**: The lowest cost model of VMs, transient and spot instances are taking advantage of a provider’s excess capacity but can be reclaimed by the provider at any time. They are typically useful for applications that don’t need to be always on or that are prohibitively expensive in any other model.  
      
    
- **Reserved instances**: Unlike pay-as-you-go models, reserved instances come with an explicit term commitment, usually of between one and three years, but are also coupled with steep discounts.  
      
    
- **Dedicated hosts**: In the case of dedicated hosts, a user typically takes on the cost of the total physical server and is billed in whatever increments the provider offers dedicated servers, typically hourly or monthly.

## Virtual machines vs. bare metal servers

Choosing a virtual machine over a physical one, also known as a bare metal server, is less about competing capabilities, and more about knowing what you need, and when you need it.

Bare metal servers are all about raw hardware, power, and isolation. They’re single-tenant, physical servers completely void of hypervisor cycles (virtualization software), and entirely dedicated to a single customer – you.

Workloads that highly prioritize performance and seclusion, like data-intensive applications and regulatory compliance mandates, are typically best suited for bare metal servers – especially when deployed over sustained periods of time.

E-commerce, ERP, CRM, SCM, and financial services applications are just a few workloads ideal for bare metal servers.

So when would you place a hypervisor on top of the bare metal hardware to make a virtual machine? When your workloads demand maximum flexibility and scalability.

Virtual machines effortlessly drive up server capacity and increase utilization – ideal for moving data from one virtual machine to another, resizing data sets, and dividing dynamic workloads.

## Virtual machines vs. [[Containers]]

The easiest way to understand a [container](https://www.ibm.com/topics/containers) is to understand how it differs from a traditional virtual machine (VM). In traditional virtualization—whether it be on-premises or in the cloud—a hypervisor is leveraged to virtualize physical hardware. Each VM then contains a guest OS, a virtual copy of the hardware that the OS requires to run, along with an application and its associated libraries and dependencies.

Instead of virtualizing the underlying hardware, containers virtualize the operating system (typically Linux) so each individual container contains _only_ the application and its libraries and dependencies. The absence of the guest OS is why containers are so lightweight and, thus, fast and portable.

Containers, and the orchestration engine that manages them, Kubernetes, are well-suited for modern, [cloud-native](https://www.ibm.com/topics/cloud-native) and [microservices](https://www.ibm.com/topics/microservices) architectures. And while containers are most commonly associated with stateless services, they can be sued for stateful services as well.

Containers are also becoming more common in hybrid cloud scenarios because they can run in a consistent fashion across laptops, cloud and traditional, on-premises IT.

The blog post "[Containers vs. VMs: What's the difference?](https://www.ibm.com/blog/containers-vs-vms/)" explains more.

The following video breaks down the basics of containerization and how it compares to using VMs:

![Containerization Explained](https://cdnsecakmi.kaltura.com/p/1773841/thumbnail/entry_id/1_mtji10i1/width/640)

Containerization Explained (8:08)

Choosing a virtual machine provider

Selecting a virtual machine and cloud provider doesn’t have to be challenging, as long as you know what to look for. The virtual machine needs to fit your workload needs and business budget, of course, but other factors play key roles between you and your virtualization environment. Below are ten things to consider when selecting a virtual machine service provider.

**Reliable support**. Ensure there’s 24/7 customer support by phone, email and chat or walk away. You want a real person on the other end of the line to help you through critical IT situations. It’s also important to note which cloud providers offer additional services for more hands-on backing.

**Managed options**. Does the cloud provider offer both unmanaged and managed solutions? If you don’t know virtualization technology in and out, consider a provider that’ll be responsible for setup, maintenance and ongoing performance monitoring.

**Software integration**. Will your virtual machine environment play well with others? Operating systems, third party software, open source technology and applications help you deliver more solutions across your business. You’ll want a virtual machine provider with both support for and strong partnerships with the industry’s most-used software suppliers. Note: Stay away from vendor lock-ins.

**High-quality network and infrastructure.** How up-to-date is the infrastructure your new virtual machine will run on? This includes dependable bare metal servers, modern data centers, and the network backbone. A cloud provider should be able to deliver its part of the deal with state-of-the-art hardware and high-speed networking technology.

**Location, location, location**. The closer the data is to your users, the less hassles you’ll run into with latency, security, and timely service delivery. A good global network of scattered data centers and POP locations is central to having data where and when you need it most.

**Backup and recovery**. What plan does your cloud provider have in place for keeping your virtual machines up and running in the face of unexpected events? Do they also provide add-on backup and redundancy options for your virtualized environment? Continuous operation is something you should take seriously.

**Scalability ease**. How fast and easy will it be for you to spin up, spin down, reserve, pause, and update your virtual machine? The word you want to hear most when it comes to virtual machine scalability is “on-demand.”

**Varied CPU configurations**. The more configurations, the better. Not every virtual machine configuration fits every workload during every season of usage. Be sure to look for a virtual machine provider that delivers varied configuration packages for both single and multi-tenant requirements.

**Security layers**. Ask your provider about them, then ask about them again. Your business data is currency in the highest form, especially when dealing with sensitive client information. Private network lines, federal data center options, built-in encryption features, and meeting regulatory compliance standards are essential to protecting your most valuable asset.

**Seamless migration support.** Your IT priorities will always evolve. This we all know. Any virtual machine provider should be able to help you lift and shift between hybrid, on-premise and off-prem environments. Look for full data ingest, over-the-network and application-led migration options.


## OS  vs Hypervisors

| **Aspect**                | **Operating System (OS)**             | **Hypervisor (Virtual Machine Monitor)** |
|---------------------------|----------------------------------------|------------------------------------------|
| **Purpose**               | Manages hardware, provides user interface, and executes applications. | Provides virtualization services to run multiple operating systems on a single machine. |
| **Hardware Interaction**  | Interacts directly with physical hardware. | Interacts with hardware but operates above it, managing resources for virtual machines. |
| **User Interface**        | Provides a user interface for user interaction. | Typically does not provide a direct user interface; management is done separately. |
| **Application Execution** | Facilitates the execution of applications and manages processes. | Facilitates the execution of multiple operating systems (virtual machines) on the same hardware. |
| **Examples**              | Windows, Linux, macOS, Android, iOS.   | VMware ESXi, Microsoft Hyper-V, KVM, Xen. |

See more [[Containers]]



