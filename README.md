## WORKING WITH EBS

### NAME:KEERTHIKA A
### REGISTER NO:212224220048

## AIM:

In this lab environment, access to AWS services and service actions might be restricted to the ones that are needed to complete the lab instructions. You might encounter errors if you attempt to access other services or perform actions beyond the ones that are described in this lab.

## OBJECTIVE:

1. Create an Amazon EBS volume
2. Attach and mount your volume to an EC2 instance
3. Create a snapshot of your volume
4. Create a new volume from your snapshot
5. Attach and mount the new volume to your EC2 instance

---

## Program

### 1. Check Available Storage

```bash
df -h
```

### 2. Create an ext3 File System

```bash
sudo mkfs -t ext3 /dev/sdb
```

### 3. Create a Mount Directory

```bash
sudo mkdir /mnt/data-store
```

### 4. Mount the EBS Volume

```bash
sudo mount /dev/sdb /mnt/data-store
```

### 5. Configure Automatic Mounting

```bash
echo "/dev/sdb   /mnt/data-store ext3 defaults,noatime 1 2" | sudo tee -a /etc/fstab
```

### 6. View the File System Configuration

```bash
cat /etc/fstab
```

### 7. Verify the Mounted Volume

```bash
df -h
```

### 8. Create a File in the EBS Volume

```bash
sudo sh -c "echo some text has been written > /mnt/data-store/file.txt"
```

### 9. Read the File

```bash
cat /mnt/data-store/file.txt
```

### 10. Delete the File

```bash
sudo mount /dev/sdc /mnt/data-store2
```

### 14. Verify Snapshot Restoration

```bash
ls /mnt/data-store2/
```

Expected output:

```text
file.txt
```

---

## Illustration:

# STEP 1:
In this step, you will create and attach an Amazon EBS volume to a new Amazon EC2 instance.You will see an existing volume that is being used by the Amazon EC2 instance. This volume has a size of 8 GiB, which makes it easy to distinguish from the volume you will create next, which will be 1 GiB in size.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/feba2ba5-cb3c-4a9b-a09e-e370ceb379cd" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/702149cc-7ed6-4855-acb3-477325ab4375" />


# STEP 2:
In this step, you will connect to the Lab EC2 instance using Session Manager.You can now attach your new volume to the Amazon EC2 instance.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/15728723-c3af-4a00-9bc7-b7cf621446b0" />


# STEP 3:
In this step, you will add the new volume to a Linux instance as an ext3 file system under the /mnt/data-store mount point.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fe4ae15e-c6d8-49e8-936a-63b1e1dc843a" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/92c0e9c2-ad43-4b9e-908f-76a6ca7ff20f" />

<img width="1917" height="125" alt="image" src="https://github.com/user-attachments/assets/b74c3030-367b-4d80-9f6e-02151ec8f7b8" />

# STEP 4:
You can create any number of point-in-time, consistent snapshots from Amazon EBS volumes at any time. Amazon EBS snapshots are stored in Amazon S3 with high durability. New Amazon EBS volumes can be created out of snapshots for cloning or restoring backups. Amazon EBS snapshots can also be easily shared among AWS users or copied over AWS regions.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e505b145-7bef-45a2-8cb0-a54c7b72c25b" />

<img width="1916" height="120" alt="image" src="https://github.com/user-attachments/assets/efd009c1-4843-4b39-9528-a35c5063668d" />


# STEP 5:

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2d39cf99-aec4-4629-92e9-a8f5bdef45af" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/528bc77c-9d24-4f59-ba82-8159eaf64867" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ec96db32-6939-40e9-b75c-c22b4e083da9" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/606121a4-febc-43a4-883b-dc66a6a07fad" />

## RESULT:
Successfully created, managed, and deleted an EBS bucket on AWS, demonstrating the ability to upload, access, and control objects within Amazon EBS.





