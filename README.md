%define VER 1.0.0
Name:           deepak-raut
Version:        %{VER}
Release:        1%{?dist}
Summary:        This is an example of createing rpm package
Group:          Development
License:        GPL
Prefix:         %{_prefix}
Source:         any
AutoReqProv:    no

%description
This is to create hello.txt file using rpm package.

%prep
echo ">>>>>>>>>>>>>Installing package<<<<<<<<<<<"
%build

%install
mkdir -p ${RPM_BUILD_ROOT}/opt/test
echo Hello world >>hello.txt
cp hello.txt ${RPM_BUILD_ROOT}/opt/test
cd ${RPM_BUILD_ROOT}/opt/test
ls
chown -R root:root ${RPM_BUILD_ROOT}/opt/test
chmod -R 755 ${RPM_BUILD_ROOT}/opt/test
cat ./hello.txt
%post
ls -lrt

echo ">>>>Installation Completed <<<"

%clean

%files
/opt/test/

%doc

%changelog# m
