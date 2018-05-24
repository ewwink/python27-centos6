
# Python 2.7 RPM built for RHEL/Centos 6.x

**Description**:  RHEL 6.x comes with Python 2.6 installed.  This project contains a SPEC file for building an RPM that compiles Python 2.7 and installs pip and virtualenv.

## Dependencies

Currently, only RHEL and CentOS 6.x have been tested.  Other dependencies are installed
via the boostrap.sh script.

## Installation
### Using our release
     wget https://github.com/ewwink/python27-centos6/releases/download/2.7.15/python27-2.7.15-2.el6.x86_64.rpm
     # Install the RPM
     yum install python27-2.7.15-2.el6.x86_64.rpm

### Build it using your machine
    git clone https://github.com/ewwink/python27-centos6.git
    cd python27-centos6
    sh bootstrap.sh
    cd ~/rpmbuild
    rpmbuild -ba SPECS/python27-alt.spec
    # Install the RPM
    sudo yum install RPMS/x86_64/python27-2.7.6-1.el6.x86_64.rpm

## Configuration

Edit the SPEC file to to update python version or make changes to the build configuration.

## Usage
    python2.7 -V
    python2.7 myscript.py

**or using virtualenv**

    /usr/local/bin/virtualenv ~/.virtualenvs/{ your_venv }
    source ~/.virtualenvs/{ your_venv }/bin/activate
    python -V
    # should return 2.7.15
**Install packages using pip, and code!**

## Known issues

- Currently, a number of compilation errors are displayed while the RPM is being
built.  This is related to the rpmbuild process itself attempting to binary
compile various Python 2.7 packages using the system Python (2.6).  So far,
this has not had any affect on the usability of the Python install.

## Getting help

If you have questions, concerns, bug reports, etc, please file an issue in this repository's Issue Tracker.

----

credit : edited from [cfpb](https://github.com/cfpb/python27-for-el6)
