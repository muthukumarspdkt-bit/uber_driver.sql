# uber_driver.sql
Mysql project 

CREATE TABLE drivers (
    driver_id INT PRIMARY KEY IDENTITY(1,1),
    driver_name VARCHAR(100) NOT NULL,
    vehicle_type VARCHAR(10) NOT NULL,
    vehicle_name VARCHAR(50) NOT NULL,
    city VARCHAR(50) NOT NULL,
    status VARCHAR(15) NOT NULL,
    issue VARCHAR(MAX),
    trip_taken INT,
    date_of_birth DATE NOT NULL,
    incentive_achieved DECIMAL(10,2) DEFAULT 0.00,
    join_date DATE NOT NULL,
    license_expiry DATE NOT NULL,
    complaints_count INT DEFAULT 0,
    late_arrivals INT DEFAULT 0,
    cancellation_rating DECIMAL(3,2) DEFAULT 0.00,
    total_earnings DECIMAL(12,2) DEFAULT 0.00,
    trips_completed INT DEFAULT 0,
    aadhar_number VARCHAR(3) NOT NULL CHECK (aadhar_number IN ('Yes', 'No')),
    pan_number VARCHAR(3) NOT NULL CHECK (pan_number IN ('Yes', 'No')),
    background_verification_status VARCHAR(3) NOT NULL CHECK (background_verification_status IN ('Yes', 'No')),
    police_verification_document VARCHAR(3) NOT NULL CHECK (police_verification_document IN ('Yes', 'No'))
);
GO

-- Insert 56 Driver Records with complete information
INSERT INTO drivers (driver_name, vehicle_type, vehicle_name, city, status, issue, trip_taken, date_of_birth, incentive_achieved, join_date, license_expiry, complaints_count, late_arrivals, cancellation_rating, total_earnings, trips_completed, aadhar_number, pan_number, background_verification_status, police_verification_document) VALUES
-- Bike drivers
('Rajesh Kumar', 'bike', 'Honda Activa', 'Bangalore', 'active', 'None', 245, '1985-03-15', 18500.00, '2022-05-10', '2026-03-15', 2, 8, 3.27, 147000.00, 245, 'Yes', 'Yes', 'Yes', 'Yes'),
('Priya Sharma', 'bike', 'TVS Jupiter', 'Mumbai', 'active', 'Low earning concern', 189, '1992-07-22', 12300.00, '2023-01-15', '2027-07-22', 5, 12, 6.35, 94500.00, 189, 'Yes', 'Yes', 'Yes', 'Yes'),
('Amit Patel', 'bike', 'Suzuki Access', 'Delhi', 'waitlisted', 'Asking extra money from customers', 45, '2008-11-10', 5200.00, '2024-03-20', '2026-11-10', 18, 15, 40.00, 22500.00, 45, 'Yes', 'No', 'No', 'No'),
('Sunita Reddy', 'bike', 'Hero Maestro', 'Hyderabad', 'rejected', 'Duplicate ID found', 12, '2009-05-18', 5000.00, '2024-06-12', '2027-05-18', 8, 5, 41.67, 6000.00, 12, 'Yes', 'No', 'No', 'No'),
('Vijay Singh', 'bike', 'Yamaha Fascino', 'Pune', 'applied', 'Under verification', 0, '1995-09-25', 5000.00, '2024-11-20', '2028-09-25', 0, 0, 0.00, 0.00, 0, 'Yes', 'Yes', 'No', 'Yes'),
('Mohammed Ali', 'bike', 'Honda Dio', 'Bangalore', 'active', 'Vehicle maintenance issue', 312, '1987-01-08', 24800.00, '2021-08-15', '2026-01-08', 4, 10, 3.21, 187200.00, 312, 'Yes', 'Yes', 'Yes', 'Yes'),
('Kavita Nair', 'bike', 'TVS Ntorq', 'Kochi', 'active', 'Health issue - diabetes management', 156, '1991-12-30', 10400.00, '2023-04-10', '2027-12-30', 3, 7, 4.49, 78000.00, 156, 'Yes', 'Yes', 'Yes', 'Yes'),
('Sneha Desai', 'bike', 'Suzuki Burgman', 'Ahmedabad', 'active', 'Personal issue - family emergency', 203, '1993-04-17', 14700.00, '2022-09-05', '2027-04-17', 4, 9, 4.43, 101500.00, 203, 'Yes', 'Yes', 'Yes', 'Yes'),
('Anjali Verma', 'bike', 'Honda Activa 6G', 'Jaipur', 'applied', 'Documents under review', 0, '2007-08-12', 5000.00, '2024-12-01', '2025-08-12', 0, 0, 0.00, 0.00, 0, 'Yes', 'No', 'No', 'No'),
('Pooja Singh', 'bike', 'TVS Jupiter ZX', 'Delhi', 'active', 'None', 278, '1989-02-28', 19600.00, '2022-03-12', '2027-02-28', 3, 11, 3.96, 139000.00, 278, 'Yes', 'Yes', 'Yes', 'Yes'),
('Pallavi Jain', 'bike', 'Hero Pleasure', 'Jaipur', 'active', 'Seasonal issue - tourist season', 167, '1994-06-05', 11200.00, '2023-06-18', '2028-06-05', 4, 8, 4.79, 83500.00, 167, 'Yes', 'Yes', 'Yes', 'Yes'),
('Seema Roy', 'bike', 'Yamaha Ray ZR', 'Guwahati', 'reactivation', 'Document issue - bank details update', 89, '1991-10-20', 6800.00, '2023-11-05', '2025-10-20', 6, 6, 6.74, 44500.00, 89, 'Yes', 'Yes', 'Yes', 'Yes'),

-- Auto drivers
('Lakshmi Iyer', 'auto', 'Bajaj RE Auto', 'Chennai', 'reactivation', 'Document issue - expired license', 134, '1983-03-12', 9500.00, '2022-07-20', '2024-03-12', 7, 9, 6.72, 67000.00, 134, 'Yes', 'Yes', 'Yes', 'Yes'),
('Deepak Mehta', 'auto', 'Piaggio Ape', 'Mumbai', 'waitlisted', 'Operating multiple vehicles with different IDs', 67, '2009-11-25', 5400.00, '2024-02-10', '2027-11-25', 22, 18, 32.84, 33500.00, 67, 'Yes', 'No', 'No', 'No'),
('Rahul Gupta', 'auto', 'Mahindra Alfa', 'Delhi', 'rejected', 'Duplicate ID - account suspended', 23, '2008-07-08', 5100.00, '2024-05-15', '2026-07-08', 14, 10, 60.87, 11500.00, 23, 'Yes', 'No', 'No', 'No'),
('Karthik Rao', 'auto', 'TVS King', 'Bangalore', 'active', 'Seasonal issue - monsoon affecting rides', 289, '1982-05-30', 21500.00, '2021-10-12', '2026-05-30', 5, 13, 4.50, 144500.00, 289, 'Yes', 'Yes', 'Yes', 'Yes'),
('Suresh Babu', 'auto', 'Bajaj Maxima', 'Chennai', 'reactivation', 'Document issue - insurance expired', 145, '1985-09-14', 10200.00, '2022-12-08', '2025-09-14', 8, 10, 6.90, 72500.00, 145, 'Yes', 'Yes', 'Yes', 'Yes'),
('Arun Kumar', 'auto', 'Piaggio Ape City', 'Bangalore', 'waitlisted', 'Customer complaints - overcharging', 56, '1987-01-22', 5600.00, '2024-01-25', '2027-01-22', 19, 15, 33.93, 28000.00, 56, 'Yes', 'Yes', 'No', 'Yes'),
('Ramesh Pillai', 'auto', 'Mahindra Treo', 'Kochi', 'rejected', 'Duplicate ID verification failed', 18, '1980-12-05', 5050.00, '2024-07-10', '2025-12-05', 11, 8, 61.11, 9000.00, 18, 'Yes', 'Yes', 'No', 'No'),
('Sandeep Joshi', 'auto', 'Bajaj RE Compact', 'Pune', 'reactivation', 'Document issue - RC renewal pending', 112, '1986-04-18', 8400.00, '2023-03-15', '2025-04-18', 6, 8, 7.14, 56000.00, 112, 'Yes', 'Yes', 'Yes', 'Yes'),
('Vikram Malhotra', 'auto', 'TVS King Deluxe', 'Chandigarh', 'applied', 'Background verification in progress', 0, '1990-08-09', 5000.00, '2024-12-05', '2028-08-09', 0, 0, 0.00, 0.00, 0, 'Yes', 'Yes', 'No', 'Yes'),
('Rekha Patel', 'auto', 'Piaggio Ape Auto', 'Ahmedabad', 'waitlisted', 'Multiple vehicle operation suspected', 72, '2010-02-28', 5700.00, '2024-04-18', '2028-02-28', 24, 20, 33.33, 36000.00, 72, 'Yes', 'No', 'No', 'No'),
('Govind Sharma', 'auto', 'Mahindra Alfa Plus', 'Indore', 'active', 'Seasonal issue - wedding season high demand', 234, '1984-06-15', 17100.00, '2022-02-20', '2027-06-15', 4, 11, 4.70, 117000.00, 234, 'Yes', 'Yes', 'Yes', 'Yes'),
('Manoj Tiwari', 'auto', 'Bajaj RE 4S', 'Varanasi', 'rejected', 'Duplicate ID - multiple accounts', 34, '1983-10-30', 5200.00, '2024-08-22', '2026-10-30', 16, 12, 47.06, 17000.00, 34, 'Yes', 'Yes', 'No', 'No'),
('Harish Bhat', 'auto', 'TVS King Duramax', 'Mangalore', 'reactivation', 'Document issue - PAN card update needed', 98, '1985-03-08', 7600.00, '2023-05-10', '2026-03-08', 5, 7, 7.14, 49000.00, 98, 'Yes', 'No', 'Yes', 'Yes'),
('Swati Kulkarni', 'auto', 'Piaggio Ape Xtra', 'Pune', 'waitlisted', 'Asking extra fare from passengers', 61, '2009-11-20', 5500.00, '2024-06-15', '2027-11-20', 21, 17, 34.43, 30500.00, 61, 'Yes', 'No', 'No', 'No'),
('Nandini Rao', 'auto', 'Mahindra Treo Zor', 'Mysore', 'applied', 'Documents submitted', 0, '1993-07-12', 5000.00, '2024-12-10', '2028-07-12', 0, 0, 0.00, 0.00, 0, 'Yes', 'Yes', 'No', 'Yes'),
('Geeta Menon', 'auto', 'Bajaj RE Electric', 'Trivandrum', 'reactivation', 'Document issue - address proof pending', 87, '1987-05-25', 6900.00, '2023-08-20', '2027-05-25', 5, 6, 6.90, 43500.00, 87, 'Yes', 'Yes', 'Yes', 'Yes'),
('Sanjay Mishra', 'auto', 'TVS King Electric', 'Bhopal', 'rejected', 'Duplicate ID found in system', 29, '1982-09-18', 5150.00, '2024-09-05', '2026-09-18', 15, 11, 51.72, 14500.00, 29, 'Yes', 'Yes', 'No', 'No'),
('Naresh Yadav', 'auto', 'Piaggio Ape E-City', 'Delhi', 'waitlisted', 'Driving multiple vehicles with different IDs', 54, '2008-01-30', 5450.00, '2024-07-20', '2026-01-30', 20, 16, 37.04, 27000.00, 54, 'Yes', 'No', 'No', 'No'),
('Usha Rani', 'auto', 'Mahindra Alfa Load', 'Ranchi', 'rejected', 'Duplicate ID verification failed', 15, '1981-12-14', 5000.00, '2024-10-15', '2025-12-14', 9, 7, 60.00, 7500.00, 15, 'Yes', 'Yes', 'No', 'No'),
('Bharti Agarwal', 'auto', 'Bajaj Qute', 'Surat', 'waitlisted', 'Customer complaints about extra charges', 48, '1990-04-22', 5400.00, '2024-08-10', '2028-04-22', 18, 14, 37.50, 24000.00, 48, 'Yes', 'Yes', 'No', 'Yes'),

-- Car drivers
('Neha Kapoor', 'car', 'Hyundai Creta', 'Mumbai', 'active', 'Low earning - night shift preference', 456, '1988-06-10', 38500.00, '2021-03-15', '2027-06-10', 6, 15, 3.29, 273600.00, 456, 'Yes', 'Yes', 'Yes', 'Yes'),
('Divya Krishnan', 'car', 'Hyundai Venue', 'Hyderabad', 'active', 'Vehicle issue - AC malfunction', 389, '1990-09-18', 31200.00, '2021-07-20', '2028-09-18', 8, 18, 4.63, 233400.00, 389, 'Yes', 'Yes', 'Yes', 'Yes'),
('Meera Devi', 'car', 'Toyota Etios', 'Lucknow', 'active', 'Health issue - back pain', 267, '1945-03-25', 20100.00, '2020-05-10', '2025-03-25', 5, 12, 4.49, 160200.00, 267, 'Yes', 'Yes', 'Yes', 'Yes'),
('Shalini Reddy', 'car', 'Honda City', 'Hyderabad', 'active', 'Low earning complaint', 412, '1989-11-08', 33800.00, '2021-09-12', '2027-11-08', 7, 16, 3.88, 247200.00, 412, 'Yes', 'Yes', 'Yes', 'Yes'),
('Anita Deshmukh', 'car', 'Toyota Innova', 'Nagpur', 'active', 'Personal issue - child care', 334, '1987-07-30', 26500.00, '2021-11-18', '2027-07-30', 6, 14, 4.19, 200400.00, 334, 'Yes', 'Yes', 'Yes', 'Yes'),
('Pradeep Nair', 'car', 'Maruti Ertiga', 'Kochi', 'active', 'Vehicle issue - tire replacement needed', 298, '1986-02-14', 23200.00, '2022-01-25', '2028-02-14', 5, 13, 4.36, 178800.00, 298, 'Yes', 'Yes', 'Yes', 'Yes'),
('Ravi Chandra', 'car', 'Hyundai Venue', 'Visakhapatnam', 'active', 'None', 367, '1991-05-20', 29400.00, '2021-12-08', '2029-05-20', 4, 11, 3.00, 220200.00, 367, 'Yes', 'Yes', 'Yes', 'Yes'),
('Ashok Kumar', 'car', 'Toyota Etios', 'Coimbatore', 'active', 'Health issue - routine checkup', 289, '1948-10-12', 22100.00, '2020-08-15', '2025-10-12', 4, 10, 3.46, 173400.00, 289, 'Yes', 'Yes', 'Yes', 'Yes'),
('Kavita Bose', 'car', 'Maruti Ertiga', 'Kolkata', 'active', 'Low earning due to area preference', 245, '1988-08-28', 18900.00, '2022-04-20', '2028-08-28', 7, 14, 5.71, 147000.00, 245, 'Yes', 'Yes', 'Yes', 'Yes'),
('Prakash Shetty', 'car', 'Toyota Innova', 'Bangalore', 'active', 'Vehicle issue - engine servicing', 501, '1983-01-05', 42800.00, '2020-06-10', '2026-01-05', 5, 17, 3.39, 300600.00, 501, 'Yes', 'Yes', 'Yes', 'Yes'),
('Madhuri Sinha', 'car', 'Hyundai Creta', 'Patna', 'applied', 'Application under review', 0, '2009-12-18', 5000.00, '2024-12-15', '2027-12-18', 0, 0, 0.00, 0.00, 0, 'Yes', 'No', 'No', 'No'),
('Dinesh Pillai', 'car', 'Honda City', 'Chennai', 'reactivation', 'Document issue - fitness certificate expired', 178, '1986-04-08', 13200.00, '2022-10-18', '2024-04-08', 8, 11, 6.18, 106800.00, 178, 'Yes', 'Yes', 'Yes', 'Yes'),
('Radha Krishna', 'car', 'Maruti Dzire', 'Hyderabad', 'active', 'Personal issue - relocation planning', 423, '1987-09-22', 34900.00, '2021-05-22', '2027-09-22', 6, 15, 3.55, 253800.00, 423, 'Yes', 'Yes', 'Yes', 'Yes'),
('Ajay Thakur', 'car', 'Hyundai Venue', 'Shimla', 'active', 'Seasonal issue - winter tourism', 198, '1990-06-15', 15100.00, '2023-02-10', '2028-06-15', 4, 9, 4.55, 118800.00, 198, 'Yes', 'Yes', 'Yes', 'Yes'),
('Mohan Das', 'car', 'Toyota Etios', 'Bhubaneswar', 'active', 'None', 312, '1950-11-30', 24300.00, '2020-09-15', '2025-11-30', 4, 12, 3.85, 187200.00, 312, 'Yes', 'Yes', 'Yes', 'Yes'),
('Kishore Kumar', 'car', 'Maruti Ertiga', 'Vijayawada', 'active', 'Health issue - eye checkup scheduled', 356, '1988-03-12', 28600.00, '2021-08-20', '2028-03-12', 5, 13, 3.65, 213600.00, 356, 'Yes', 'Yes', 'Yes', 'Yes'),
('Brijesh Pandey', 'car', 'Honda Amaze', 'Kanpur', 'active', 'Low earning - switching to peak hours', 234, '2010-07-25', 17500.00, '2024-05-12', '2028-07-25', 6, 11, 4.70, 140400.00, 234, 'Yes', 'No', 'No', 'No'),
('Archana Iyer', 'car', 'Maruti Dzire', 'Kochi', 'applied', 'Waiting for onboarding', 0, '1994-02-08', 5000.00, '2024-12-18', '2029-02-08', 0, 0, 0.00, 0.00, 0, 'Yes', 'Yes', 'No', 'Yes'),
('Nitesh Agarwal', 'car', 'Toyota Innova', 'Mumbai', 'active', 'Vehicle issue - brake system check', 489, '1984-10-18', 40700.00, '2020-11-10', '2028-10-18', 6, 16, 3.27, 293400.00, 489, 'Yes', 'Yes', 'Yes', 'Yes'),
('Shilpa Hegde', 'car', 'Hyundai Creta', 'Bangalore', 'waitlisted', 'Multiple account operation suspected', 78, '2009-05-30', 6200.00, '2024-08-20', '2027-05-30', 28, 22, 35.90, 46800.00, 78, 'Yes', 'No', 'No', 'No'),
('Ranjit Singh', 'car', 'Honda City', 'Amritsar', 'active', 'Seasonal issue - festival rush', 401, '1986-08-14', 33200.00, '2021-10-15', '2028-08-14', 6, 14, 3.49, 240600.00, 401, 'Yes', 'Yes', 'Yes', 'Yes'),
('Vaishali Chopra', 'car', 'Maruti Swift', 'Delhi', 'rejected', 'Duplicate ID - policy violation', 41, '2008-12-22', 5300.00, '2024-09-10', '2026-12-22', 19, 15, 46.34, 24600.00, 41, 'Yes', 'No', 'No', 'No'),
('Ganesh Murthy', 'car', 'Hyundai Venue', 'Chennai', 'active', 'Personal issue - health insurance claim', 378, '1987-04-05', 30500.00, '2021-11-22', '2027-04-05', 6, 15, 3.97, 226800.00, 378, 'Yes', 'Yes', 'Yes', 'Yes'),
('Sunil Kapoor', 'car', 'Maruti Swift', 'Bangalore', 'active', 'None', 445, '1989-09-28', 37200.00, '2021-04-18', '2027-09-28', 5, 13, 2.92, 267000.00, 445, 'Yes', 'Yes', 'Yes', 'Yes'),
('Preeti Agarwal', 'car', 'Honda Jazz', 'Mumbai', 'active', 'Low earning - peak hour strategy', 412, '1991-01-15', 33800.00, '2021-06-25', '2029-01-15', 7, 16, 3.88, 247200.00, 412, 'Yes', 'Yes', 'Yes', 'Yes'),
('Anil Verma', 'car', 'Hyundai i20', 'Delhi', 'active', 'Vehicle issue - suspension check needed', 367, '1986-06-20', 29400.00, '2021-12-30', '2028-06-20', 6, 14, 3.81, 220200.00, 367, 'Yes', 'Yes', 'Yes', 'Yes'); 'Verified', 'Yes'),
('Suresh Babu', 'auto', 'Bajaj Maxima', 'Chennai', 'reactivation', 'Document issue - insurance expired', 145, '1985-09-14', 10200.00, '2022-12-08', '2025-09-14', 8, 10, 6.90, 72500.00, 145, '890123456890', 'HIJSB2345D', 'Verified', 'Yes'),
('Arun Kumar', 'auto', 'Piaggio Ape City', 'Bangalore', 'waitlisted', 'Customer complaints - overcharging', 56, '1987-01-22', 5600.00, '2024-01-25', '2027-01-22', 19, 15, 33.93, 28000.00, 56, '901234567901', 'KLMAK3456E', 'Under Review', 'Yes'),
('Ramesh Pillai', 'auto', 'Mahindra Treo', 'Kochi', 'rejected', 'Duplicate ID verification failed', 18, '1980-12-05', 5050.00, '2024-07-10', '2025-12-05', 11, 8, 61.11, 9000.00, 18, '012345678012', 'NOPPR4567F', 'Failed', 'No'),
('Sandeep Joshi', 'auto', 'Bajaj RE Compact', 'Pune', 'reactivation', 'Document issue - RC renewal pending', 112, '1986-04-18', 8400.00, '2023-03-15', '2025-04-18', 6, 8, 7.14, 56000.00, 112, '123456789123', 'QRSSJ5678G', 'Verified', 'Yes'),
('Vikram Malhotra', 'auto', 'TVS King Deluxe', 'Chandigarh', 'applied', 'Background verification in progress', 0, '1990-08-09', 5000.00, '2024-12-05', '2028-08-09', 0, 0, 0.00, 0.00, 0, '234567890234', 'TUVVM6789H', 'In Progress', 'Yes'),
('Rekha Patel', 'auto', 'Piaggio Ape Auto', 'Ahmedabad', 'waitlisted', 'Multiple vehicle operation suspected', 72, '2010-02-28', 5700.00, '2024-04-18', '2028-02-28', 24, 20, 33.33, 36000.00, 72, '345678901345', NULL, 'Under Review', 'No'),
('Govind Sharma', 'auto', 'Mahindra Alfa Plus', 'Indore', 'active', 'Seasonal issue - wedding season high demand', 234, '1984-06-15', 17100.00, '2022-02-20', '2027-06-15', 4, 11, 4.70, 117000.00, 234, '456789012456', 'WXYGS7890I', 'Verified', 'Yes'),
('Manoj Tiwari', 'auto', 'Bajaj RE 4S', 'Varanasi', 'rejected', 'Duplicate ID - multiple accounts', 34, '1983-10-30', 5200.00, '2024-08-22', '2026-10-30', 16, 12, 47.06, 17000.00, 34, '567890123567', 'ZABMT8901J', 'Failed', 'No'),
('Harish Bhat', 'auto', 'TVS King Duramax', 'Mangalore', 'reactivation', 'Document issue - PAN card update needed', 98, '1985-03-08', 7600.00, '2023-05-10', '2026-03-08', 5, 7, 7.14, 49000.00, 98, '678901234678', 'BCDHB9012K', 'Verified', 'Yes'),
('Swati Kulkarni', 'auto', 'Piaggio Ape Xtra', 'Pune', 'waitlisted', 'Asking extra fare from passengers', 61, '2009-11-20', 5500.00, '2024-06-15', '2027-11-20', 21, 17, 34.43, 30500.00, 61, '789012345789', NULL, 'Under Review', 'No'),
('Nandini Rao', 'auto', 'Mahindra Treo Zor', 'Mysore', 'applied', 'Documents submitted', 0, '1993-07-12', 5000.00, '2024-12-10', '2028-07-12', 0, 0, 0.00, 0.00, 0, '890123456890', 'EFGNR0123L', 'In Progress', 'Yes'),
('Geeta Menon', 'auto', 'Bajaj RE Electric', 'Trivandrum', 'reactivation', 'Document issue - address proof pending', 87, '1987-05-25', 6900.00, '2023-08-20', '2027-05-25', 5, 6, 6.90, 43500.00, 87, '901234567901', 'HIJGM1234M', 'Verified', 'Yes'),
('Sanjay Mishra', 'auto', 'TVS King Electric', 'Bhopal', 'rejected', 'Duplicate ID found in system', 29, '1982-09-18', 5150.00, '2024-09-05', '2026-09-18', 15, 11, 51.72, 14500.00, 29, '012345678012', 'KLMSM2345N', 'Failed', 'No'),
('Naresh Yadav', 'auto', 'Piaggio Ape E-City', 'Delhi', 'waitlisted', 'Driving multiple vehicles with different IDs', 54, '2008-01-30', 5450.00, '2024-07-20', '2026-01-30', 20, 16, 37.04, 27000.00, 54, '123456789123', NULL, 'Under Review', 'No'),
('Usha Rani', 'auto', 'Mahindra Alfa Load', 'Ranchi', 'rejected', 'Duplicate ID verification failed', 15, '1981-12-14', 5000.00, '2024-10-15', '2025-12-14', 9, 7, 60.00, 7500.00, 15, '234567890234', 'NOPUR3456O', 'Failed', 'No'),
('Bharti Agarwal', 'auto', 'Bajaj Qute', 'Surat', 'waitlisted', 'Customer complaints about extra charges', 48, '1990-04-22', 5400.00, '2024-08-10', '2028-04-22', 18, 14, 37.50, 24000.00, 48, '345678901345', 'PQRBA4567P', 'Under Review', 'Yes'),

-- Car drivers
('Neha Kapoor', 'car', 'Hyundai Creta', 'Mumbai', 'active', 'Low earning - night shift preference', 456, '1988-06-10', 38500.00, '2021-03-15', '2027-06-10', 6, 15, 3.29, 273600.00, 456, '456789012456', 'STUNK5678Q', 'Verified', 'Yes'),
('Divya Krishnan', 'car', 'Hyundai Venue', 'Hyderabad', 'active', 'Vehicle issue - AC malfunction', 389, '1990-09-18', 31200.00, '2021-07-20', '2028-09-18', 8, 18, 4.63, 233400.00, 389, '567890123567', 'VWXDK6789R', 'Verified', 'Yes'),
('Meera Devi', 'car', 'Toyota Etios', 'Lucknow', 'active', 'Health issue - back pain', 267, '1945-03-25', 20100.00, '2020-05-10', '2025-03-25', 5, 12, 4.49, 160200.00, 267, '678901234678', 'YZAMD7890S', 'Verified', 'Yes'),
('Shalini Reddy', 'car', 'Honda City', 'Hyderabad', 'active', 'Low earning complaint', 412, '1989-11-08', 33800.00, '2021-09-12', '2027-11-08', 7, 16, 3.88, 247200.00, 412, '789012345789', 'BCDSR8901T', 'Verified', 'Yes'),
('Anita Deshmukh', 'car', 'Toyota Innova', 'Nagpur', 'active', 'Personal issue - child care', 334, '1987-07-30', 26500.00, '2021-11-18', '2027-07-30', 6, 14, 4.19, 200400.00, 334, '890123456890', 'EFGAD9012U', 'Verified', 'Yes'),
('Pradeep Nair', 'car', 'Maruti Ertiga', 'Kochi', 'active', 'Vehicle issue - tire replacement needed', 298, '1986-02-14', 23200.00, '2022-01-25', '2028-02-14', 5, 13, 4.36, 178800.00, 298, '901234567901', 'HIJPN0123V', 'Verified', 'Yes'),
('Ravi Chandra', 'car', 'Hyundai Venue', 'Visakhapatnam', 'active', 'None', 367, '1991-05-20', 29400.00, '2021-12-08', '2029-05-20', 4, 11, 3.00, 220200.00, 367, '012345678012', 'KLMRC1234W', 'Verified', 'Yes'),
('Ashok Kumar', 'car', 'Toyota Etios', 'Coimbatore', 'active', 'Health issue - routine checkup', 289, '1948-10-12', 22100.00, '2020-08-15', '2025-10-12', 4, 10, 3.46, 173400.00, 289, '123456789123', 'NOPAK2345X', 'Verified', 'Yes'),
('Kavita Bose', 'car', 'Maruti Ertiga', 'Kolkata', 'active', 'Low earning due to area preference', 245, '1988-08-28', 18900.00, '2022-04-20', '2028-08-28', 7, 14, 5.71, 147000.00, 245, '234567890234', 'QRSKB3456Y', 'Verified', 'Yes'),
('Prakash Shetty', 'car', 'Toyota Innova', 'Bangalore', 'active', 'Vehicle issue - engine servicing', 501, '1983-01-05', 42800.00, '2020-06-10', '2026-01-05', 5, 17, 3.39, 300600.00, 501, '345678901345', 'TUVPS4567Z', 'Verified', 'Yes'),
('Madhuri Sinha', 'car', 'Hyundai Creta', 'Patna', 'applied', 'Application under review', 0, '2009-12-18', 5000.00, '2024-12-15', '2027-12-18', 0, 0, 0.00, 0.00, 0, '456789012456', NULL, 'In Progress', 'No'),
('Dinesh Pillai', 'car', 'Honda City', 'Chennai', 'reactivation', 'Document issue - fitness certificate expired', 178, '1986-04-08', 13200.00, '2022-10-18', '2024-04-08', 8, 11, 6.18, 106800.00, 178, '567890123567', 'WXYDP5678A', 'Verified', 'Yes'),
('Radha Krishna', 'car', 'Maruti Dzire', 'Hyderabad', 'active', 'Personal issue - relocation planning', 423, '1987-09-22', 34900.00, '2021-05-22', '2027-09-22', 6, 15, 3.55, 253800.00, 423, '678901234678', 'ZABR6789B', 'Verified', 'Yes'),
('Ajay Thakur', 'car', 'Hyundai Venue', 'Shimla', 'active', 'Seasonal issue - winter tourism', 198, '1990-06-15', 15100.00, '2023-02-10', '2028-06-15', 4, 9, 4.55, 118800.00, 198, '789012345789', 'BCDAT7890C', 'Verified', 'Yes'),
('Mohan Das', 'car', 'Toyota Etios', 'Bhubaneswar', 'active', 'None', 312, '1950-11-30', 24300.00, '2020-09-15', '2025-11-30', 4, 12, 3.85, 187200.00, 312, '890123456890', 'EFGMD8901D', 'Verified', 'Yes'),
('Kishore Kumar', 'car', 'Maruti Ertiga', 'Vijayawada', 'active', 'Health issue - eye checkup scheduled', 356, '1988-03-12', 28600.00, '2021-08-20', '2028-03-12', 5, 13, 3.65, 213600.00, 356, '901234567901', 'HIJKK9012E', 'Verified', 'Yes'),
('Brijesh Pandey', 'car', 'Honda Amaze', 'Kanpur', 'active', 'Low earning - switching to peak hours', 234, '2010-07-25', 17500.00, '2024-05-12', '2028-07-25', 6, 11, 4.70, 140400.00, 234, '012345678012', NULL, 'In Progress', 'No'),
('Archana Iyer', 'car', 'Maruti Dzire', 'Kochi', 'applied', 'Waiting for onboarding', 0, '1994-02-08', 5000.00, '2024-12-18', '2029-02-08', 0, 0, 0.00, 0.00, 0, '123456789123', 'KLMAI0123F', 'In Progress', 'Yes'),
('Nitesh Agarwal', 'car', 'Toyota Innova', 'Mumbai', 'active', 'Vehicle issue - brake system check', 489, '1984-10-18', 40700.00, '2020-11-10', '2028-10-18', 6, 16, 3.27, 293400.00, 489, '234567890234', 'NOPNA1234G', 'Verified', 'Yes'),
('Shilpa Hegde', 'car', 'Hyundai Creta', 'Bangalore', 'waitlisted', 'Multiple account operation suspected', 78, '2009-05-30', 6200.00, '2024-08-20', '2027-05-30', 28, 22, 35.90, 46800.00, 78, '345678901345', NULL, 'Under Review', 'No'),
('Ranjit Singh', 'car', 'Honda City', 'Amritsar', 'active', 'Seasonal issue - festival rush', 401, '1986-08-14', 33200.00, '2021-10-15', '2028-08-14', 6, 14, 3.49, 240600.00, 401, '456789012456', 'QRSRS2345H', 'Verified', 'Yes'),
('Vaishali Chopra', 'car', 'Maruti Swift', 'Delhi', 'rejected', 'Duplicate ID - policy violation', 41, '2008-12-22', 5300.00, '2024-09-10', '2026-12-22', 19, 15, 46.34, 24600.00, 41, '567890123567', NULL, 'Failed', 'No'),
('Ganesh Murthy', 'car', 'Hyundai Venue', 'Chennai', 'active', 'Personal issue - health insurance claim', 378, '1987-04-05', 30500.00, '2021-11-22', '2027-04-05', 6, 15, 3.97, 226800.00, 378, '678901234678', 'TUVGM3456I', 'Verified', 'Yes'),
('Sunil Kapoor', 'car', 'Maruti Swift', 'Bangalore', 'active', 'None', 445, '1989-09-28', 37200.00, '2021-04-18', '2027-09-28', 5, 13, 2.92, 267000.00, 445, '789012345789', 'WXYSK4567J', 'Verified', 'Yes'),
('Preeti Agarwal', 'car', 'Honda Jazz', 'Mumbai', 'active', 'Low earning - peak hour strategy', 412, '1991-01-15', 33800.00, '2021-06-25', '2029-01-15', 7, 16, 3.88, 247200.00, 412, '890123456890', 'ZABPA5678K', 'Verified', 'Yes'),
('Anil Verma', 'car', 'Hyundai i20', 'Delhi', 'active', 'Vehicle issue - suspension check needed', 367, '1986-06-20', 29400.00, '2021-12-30', '2028-06-20', 6, 14, 3.81, 220200.00, 367, '901234567901', 'BCDAV6789L', 'Verified', 'Yes');
GO

--SELECT, COUNT(*) as driver_count
--FROM drivers
--GROUP BY status
--ORDER BY driver_count DESC;

SELECT
    driver_name,
    city,
    vehicle_name,
    issue,
    status
FROM drivers
WHERE status = 'active';

SELECT vehicle_type, COUNT(*) as active_count
FROM drivers
WHERE status = 'active'
GROUP BY vehicle_type;


SELECT status AS dp_status, COUNT(*) AS driver_count
FROM drivers
GROUP BY status;

SELECT*
FROM drivers
where  city in ('Chennai') ;

SELECT DVP.city, DVP.vehicle_name
FROM drivers AS DVP
WHERE DVP.vehicle_name LIKE '%Bajaj%';

SELECT 
    city,SUM(trip_taken) AS total_trips_by_city
FROM drivers
GROUP BY city
ORDER BY total_trips_by_city DESC;

CREATE TABLE agent_connections (
    connection_id INT PRIMARY KEY IDENTITY(1,1),
    driver_id INT NOT NULL,
    agent_name VARCHAR(100) NOT NULL,
    connect_date DATE NOT NULL,
    connect_time TIME NOT NULL,
    driver_issue VARCHAR(100) NOT NULL,
    call_disconnect_reason VARCHAR(100),
    expected_drive_date DATE,
    expected_drive_time TIME,
    resolution_status VARCHAR(50) DEFAULT 'pending',
    notes VARCHAR(MAX),
    created_at DATETIME2 DEFAULT GETDATE(),
    FOREIGN KEY (driver_id) REFERENCES drivers(driver_id),
    CHECK (driver_issue IN ('low earning', 'out of station', 'low demand', 'accident', 'need other trip', 'doc issue', 'rider issue', 'support issue', 'seasonal issue', 'vehicle issue', 'call disconnect', 'legal issue')),
    CHECK (call_disconnect_reason IS NULL OR call_disconnect_reason IN ('abusive words', 'followup', 'language issue', 'wrong number'))
);
GO

-- Insert agent connection records for ALL 56 drivers
INSERT INTO agent_connections (driver_id, agent_name, connect_date, connect_time, driver_issue, call_disconnect_reason, expected_drive_date, expected_drive_time, resolution_status, notes) VALUES
-- Driver 1: Rajesh Kumar (bike, Bangalore, active, 245 trips)
(1, 'Ankit Sharma', '2024-12-15', '10:30:00', 'support issue', NULL, '2024-12-15', '14:00:00', 'resolved', 'Routine check-in, driver doing well'),
(1, 'Priya Reddy', '2024-12-20', '09:15:00', 'low demand', NULL, '2024-12-20', '11:00:00', 'resolved', 'Provided route optimization tips'),
(1, 'Meera Iyer', '2024-12-23', '16:45:00', 'need other trip', NULL, '2024-12-24', '08:00:00', 'resolved', 'Airport rides preference enabled'),

-- Driver 2: Priya Sharma (bike, Mumbai, active, Low earning concern, 189 trips)
(2, 'Rahul Desai', '2024-12-10', '14:20:00', 'low earning', NULL, '2024-12-11', '08:00:00', 'in_progress', 'Analyzing earning patterns'),
(2, 'Ankit Sharma', '2024-12-18', '11:45:00', 'low earning', NULL, '2024-12-18', '18:00:00', 'resolved', 'Peak hour strategy implemented'),
(2, 'Meera Iyer', '2024-12-22', '16:30:00', 'low earning', NULL, '2024-12-23', '07:00:00', 'pending', 'Following up on earnings improvement'),

-- Driver 3: Amit Patel (bike, Delhi, waitlisted, Asking extra money, 45 trips)
(3, 'Kavita Singh', '2024-11-25', '13:10:00', 'rider issue', NULL, NULL, NULL, 'under_review', 'Multiple customer complaints'),
(3, 'Suresh Kumar', '2024-12-05', '10:00:00', 'rider issue', NULL, NULL, NULL, 'warning_issued', 'Final warning for overcharging'),
(3, 'Rahul Desai', '2024-12-19', '15:20:00', 'support issue', NULL, '2024-12-25', '10:00:00', 'pending', 'Reactivation request under review'),
(3, 'Ankit Sharma', '2024-12-22', '11:00:00', 'call disconnect', 'followup', '2024-12-26', '09:00:00', 'pending', 'Following up on behavior improvement'),

-- Driver 4: Sunita Reddy (bike, Hyderabad, rejected, Duplicate ID, 12 trips)
(4, 'Meera Iyer', '2024-11-20', '11:30:00', 'legal issue', NULL, NULL, NULL, 'rejected', 'Duplicate ID - cannot proceed'),
(4, 'Kavita Singh', '2024-12-08', '14:15:00', 'legal issue', NULL, NULL, NULL, 'rejected', 'Appeal denied due to policy violation'),

-- Driver 5: Vijay Singh (bike, Pune, applied, Under verification, 0 trips)
(5, 'Ankit Sharma', '2024-12-18', '14:00:00', 'doc issue', NULL, '2024-12-22', '09:00:00', 'in_progress', 'Background verification ongoing'),
(5, 'Priya Reddy', '2024-12-21', '10:30:00', 'call disconnect', 'followup', '2024-12-23', '10:00:00', 'pending', 'Document submission reminder'),

-- Driver 6: Mohammed Ali (bike, Bangalore, active, Vehicle maintenance, 312 trips)
(6, 'Priya Reddy', '2024-12-12', '09:00:00', 'vehicle issue', NULL, '2024-12-14', '08:00:00', 'resolved', 'Vehicle serviced successfully'),
(6, 'Ankit Sharma', '2024-12-21', '14:45:00', 'support issue', NULL, '2024-12-21', '16:00:00', 'resolved', 'Bonus points inquiry resolved'),
(6, 'Rahul Desai', '2024-12-23', '10:20:00', 'vehicle issue', NULL, '2024-12-24', '09:00:00', 'pending', 'Scheduled maintenance reminder'),

-- Driver 7: Kavita Nair (bike, Kochi, active, Health issue - diabetes, 156 trips)
(7, 'Rahul Desai', '2024-12-08', '10:30:00', 'support issue', NULL, '2024-12-10', '12:00:00', 'resolved', 'Flexible scheduling arranged'),
(7, 'Kavita Singh', '2024-12-17', '13:20:00', 'out of station', NULL, '2024-12-23', '09:00:00', 'approved', 'Medical checkup leave approved'),
(7, 'Meera Iyer', '2024-12-22', '09:45:00', 'call disconnect', 'followup', '2024-12-24', '10:00:00', 'pending', 'Health status follow-up'),

-- Driver 8: Sneha Desai (bike, Ahmedabad, active, Personal issue - family emergency, 203 trips)
(8, 'Meera Iyer', '2024-12-13', '11:45:00', 'out of station', NULL, '2024-12-18', '08:00:00', 'approved', 'Family emergency leave granted'),
(8, 'Suresh Kumar', '2024-12-20', '09:30:00', 'call disconnect', 'followup', '2024-12-21', '10:00:00', 'resolved', 'Driver returned to service'),
(8, 'Ankit Sharma', '2024-12-23', '15:00:00', 'support issue', NULL, '2024-12-24', '08:00:00', 'resolved', 'Wellness check completed'),

-- Driver 9: Anjali Verma (bike, Jaipur, applied, Documents under review, 0 trips)
(9, 'Ankit Sharma', '2024-12-16', '15:20:00', 'doc issue', NULL, NULL, NULL, 'in_progress', 'Documents verification in progress'),
(9, 'Priya Reddy', '2024-12-22', '10:00:00', 'call disconnect', 'language issue', NULL, NULL, 'pending', 'Need Hindi support for better communication'),

-- Driver 10: Pooja Singh (bike, Delhi, active, None, 278 trips)
(10, 'Rahul Desai', '2024-12-14', '16:30:00', 'low demand', NULL, '2024-12-15', '07:00:00', 'resolved', 'Peak zone recommendations provided'),
(10, 'Kavita Singh', '2024-12-21', '12:15:00', 'seasonal issue', NULL, '2024-12-22', '09:00:00', 'resolved', 'Winter demand patterns explained'),
(10, 'Ankit Sharma', '2024-12-23', '14:30:00', 'support issue', NULL, '2024-12-24', '08:00:00', 'resolved', 'Regular performance check'),

-- Driver 11: Pallavi Jain (bike, Jaipur, active, Seasonal - tourist season, 167 trips)
(11, 'Meera Iyer', '2024-12-09', '13:40:00', 'seasonal issue', NULL, '2024-12-10', '10:00:00', 'resolved', 'Tourist season surge pricing activated'),
(11, 'Ankit Sharma', '2024-12-19', '11:00:00', 'low earning', NULL, '2024-12-20', '08:00:00', 'resolved', 'Tourist hotspot routes optimized'),
(11, 'Priya Reddy', '2024-12-23', '16:20:00', 'seasonal issue', NULL, '2024-12-24', '09:00:00', 'resolved', 'Peak season bonus explained'),

-- Driver 12: Seema Roy (bike, Guwahati, reactivation, Document - bank details, 89 trips)
(12, 'Suresh Kumar', '2024-12-05', '10:20:00', 'doc issue', NULL, NULL, NULL, 'pending', 'Bank details update required'),
(12, 'Priya Reddy', '2024-12-18', '14:30:00', 'doc issue', NULL, '2024-12-22', '09:00:00', 'in_progress', 'Bank documents uploaded'),
(12, 'Ankit Sharma', '2024-12-23', '11:30:00', 'doc issue', NULL, '2024-12-26', '08:00:00', 'pending', 'Final verification pending'),

-- Driver 13: Lakshmi Iyer (auto, Chennai, reactivation, Document - expired license, 134 trips)
(13, 'Suresh Kumar', '2024-12-01', '11:00:00', 'doc issue', NULL, NULL, NULL, 'pending', 'License renewal required'),
(13, 'Meera Iyer', '2024-12-15', '09:30:00', 'doc issue', NULL, '2024-12-20', '08:00:00', 'in_progress', 'License renewed, verification ongoing'),
(13, 'Ankit Sharma', '2024-12-22', '10:15:00', 'support issue', NULL, '2024-12-24', '07:00:00', 'pending', 'Reactivation almost complete'),

-- Driver 14: Deepak Mehta (auto, Mumbai, waitlisted, Multiple vehicles, 67 trips)
(14, 'Kavita Singh', '2024-11-28', '15:40:00', 'legal issue', NULL, NULL, NULL, 'under_investigation', 'Policy violation investigation'),
(14, 'Rahul Desai', '2024-12-10', '14:00:00', 'legal issue', NULL, NULL, NULL, 'warning_issued', 'Account suspended'),
(14, 'Suresh Kumar', '2024-12-19', '16:15:00', 'call disconnect', 'abusive words', NULL, NULL, 'escalated', 'Inappropriate language used'),

-- Driver 15: Rahul Gupta (auto, Delhi, rejected, Duplicate ID, 23 trips)
(15, 'Meera Iyer', '2024-11-22', '12:45:00', 'legal issue', NULL, NULL, NULL, 'rejected', 'Account permanently suspended'),
(15, 'Kavita Singh', '2024-12-08', '10:30:00', 'call disconnect', 'abusive words', NULL, NULL, 'rejected', 'Appeal denied'),

-- Driver 16: Karthik Rao (auto, Bangalore, active, Seasonal - monsoon, 289 trips)
(16, 'Priya Reddy', '2024-12-11', '08:45:00', 'seasonal issue', NULL, '2024-12-11', '11:00:00', 'resolved', 'Monsoon safety tips provided'),
(16, 'Ankit Sharma', '2024-12-19', '16:20:00', 'low earning', NULL, '2024-12-20', '09:00:00', 'resolved', 'Incentive programs explained'),
(16, 'Rahul Desai', '2024-12-23', '13:10:00', 'seasonal issue', NULL, '2024-12-24', '08:00:00', 'resolved', 'Monsoon surge bonus activated'),

-- Driver 17: Suresh Babu (auto, Chennai, reactivation, Document - insurance, 145 trips)
(17, 'Meera Iyer', '2024-12-03', '12:30:00', 'doc issue', NULL, NULL, NULL, 'pending', 'Insurance renewal pending'),
(17, 'Suresh Kumar', '2024-12-18', '10:00:00', 'doc issue', NULL, '2024-12-22', '08:00:00', 'in_progress', 'Insurance renewed, uploading docs'),
(17, 'Ankit Sharma', '2024-12-23', '14:45:00', 'doc issue', NULL, '2024-12-25', '09:00:00', 'pending', 'Final verification stage'),

-- Driver 18: Arun Kumar (auto, Bangalore, waitlisted, Customer complaints, 56 trips)
(18, 'Rahul Desai', '2024-11-30', '13:20:00', 'rider issue', NULL, NULL, NULL, 'under_review', 'Overcharging complaints received'),
(18, 'Kavita Singh', '2024-12-16', '15:45:00', 'rider issue', NULL, NULL, NULL, 'warning_issued', 'Final warning issued'),
(18, 'Meera Iyer', '2024-12-22', '11:30:00', 'support issue', NULL, '2024-12-28', '10:00:00', 'pending', 'Behavior improvement required'),

-- Driver 19: Ramesh Pillai (auto, Kochi, rejected, Duplicate ID, 18 trips)
(19, 'Ankit Sharma', '2024-11-18', '11:15:00', 'legal issue', NULL, NULL, NULL, 'rejected', 'Duplicate ID verification failed'),

-- Driver 20: Sandeep Joshi (auto, Pune, reactivation, Document - RC renewal, 112 trips)
(20, 'Priya Reddy', '2024-12-07', '14:00:00', 'doc issue', NULL, NULL, NULL, 'pending', 'RC renewal pending'),
(20, 'Meera Iyer', '2024-12-20', '10:30:00', 'doc issue', NULL, '2024-12-24', '09:00:00', 'in_progress', 'RC documents submitted'),
(20, 'Suresh Kumar', '2024-12-23', '15:20:00', 'doc issue', NULL, '2024-12-26', '08:00:00', 'pending', 'Awaiting RTO verification'),

-- Driver 21: Vikram Malhotra (auto, Chandigarh, applied, Background verification, 0 trips)
(21, 'Suresh Kumar', '2024-12-12', '09:45:00', 'doc issue', NULL, NULL, NULL, 'in_progress', 'Background check ongoing'),
(21, 'Ankit Sharma', '2024-12-21', '11:20:00', 'call disconnect', 'wrong number', NULL, NULL, 'resolved', 'Contact updated, will reconnect'),

-- Driver 22: Rekha Patel (auto, Ahmedabad, waitlisted, Multiple vehicle operation, 72 trips)
(22, 'Kavita Singh', '2024-12-02', '16:30:00', 'legal issue', NULL, NULL, NULL, 'under_investigation', 'Multiple accounts suspected'),
(22, 'Rahul Desai', '2024-12-17', '13:50:00', 'legal issue', NULL, NULL, NULL, 'warning_issued', 'Investigation in progress'),
(22, 'Suresh Kumar', '2024-12-23', '10:40:00', 'call disconnect', 'followup', NULL, NULL, 'pending', 'Awaiting investigation results'),

-- Driver 23: Govind Sharma (auto, Indore, active, Seasonal - wedding season, 234 trips)
(23, 'Priya Reddy', '2024-12-10', '10:15:00', 'seasonal issue', NULL, '2024-12-11', '08:00:00', 'resolved', 'Wedding season surge activated'),
(23, 'Meera Iyer', '2024-12-20', '15:30:00', 'low earning', NULL, '2024-12-21', '09:00:00', 'resolved', 'Peak wedding hours optimized'),
(23, 'Ankit Sharma', '2024-12-23', '12:00:00', 'seasonal issue', NULL, '2024-12-24', '08:00:00', 'resolved', 'Festival bonus explained'),

-- Driver 24: Manoj Tiwari (auto, Varanasi, rejected, Duplicate ID, 34 trips)
(24, 'Suresh Kumar', '2024-11-25', '12:00:00', 'legal issue', NULL, NULL, NULL, 'rejected', 'Multiple accounts found'),

-- Driver 25: Harish Bhat (auto, Mangalore, reactivation, Document - PAN card, 98 trips)
(25, 'Ankit Sharma', '2024-12-04', '11:30:00', 'doc issue', NULL, NULL, NULL, 'pending', 'PAN card update needed'),
(25, 'Priya Reddy', '2024-12-19', '14:15:00', 'doc issue', NULL, '2024-12-23', '10:00:00', 'in_progress', 'PAN card updated'),
(25, 'Meera Iyer', '2024-12-23', '16:00:00', 'doc issue', NULL, '2024-12-25', '09:00:00', 'pending', 'Verification in progress'),

-- Driver 26: Swati Kulkarni (auto, Pune, waitlisted, Asking extra fare, 61 trips)
(26, 'Kavita Singh', '2024-12-01', '15:00:00', 'rider issue', NULL, NULL, NULL, 'under_review', 'Extra fare complaints'),
(26, 'Rahul Desai', '2024-12-18', '10:45:00', 'rider issue', NULL, NULL, NULL, 'warning_issued', 'Final warning issued'),
(26, 'Suresh Kumar', '2024-12-23', '13:30:00', 'support issue', NULL, '2024-12-28', '10:00:00', 'pending', 'Monitoring behavior'),

-- Driver 27: Nandini Rao (auto, Mysore, applied, Documents submitted, 0 trips)
(27, 'Meera Iyer', '2024-12-14', '10:20:00', 'doc issue', NULL, NULL, NULL, 'in_progress', 'Document verification ongoing'),
(27, 'Ankit Sharma', '2024-12-22', '14:30:00', 'support issue', NULL, '2024-12-27', '09:00:00', 'pending', 'Onboarding scheduled'),

-- Driver 28: Geeta Menon (auto, Trivandrum, reactivation, Document - address proof, 87 trips)
(28, 'Meera Iyer', '2024-12-06', '13:20:00', 'doc issue', NULL, NULL, NULL, 'pending', 'Address proof required'),
(28, 'Suresh Kumar', '2024-12-21', '09:50:00', 'doc issue', NULL, '2024-12-25', '08:00:00', 'in_progress', 'Address proof submitted'),
(28, 'Priya Reddy', '2024-12-23', '15:40:00', 'doc issue', NULL, '2024-12-26', '09:00:00', 'pending', 'Final check pending'),

-- Driver 29: Sanjay Mishra (auto, Bhopal, rejected, Duplicate ID, 29 trips)
(29, 'Ankit Sharma', '2024-11-20', '14:30:00', 'legal issue', NULL, NULL, NULL, 'rejected', 'Duplicate ID confirmed'),

-- Driver 30: Naresh Yadav (auto, Delhi, waitlisted, Multiple vehicles, 54 trips)
(30, 'Priya Reddy', '2024-12-03', '11:40:00', 'legal issue', NULL, NULL, NULL, 'under_investigation', 'Multiple accounts suspected'),
(30, 'Kavita Singh', '2024-12-19', '16:00:00', 'call disconnect', 'abusive words', NULL, NULL, 'escalated', 'Aggressive behavior'),
(30, 'Rahul Desai', '2024-12-23', '10:15:00', 'legal issue', NULL, NULL, NULL, 'warning_issued', 'Under review'),

-- Driver 31: Usha Rani (auto, Ranchi, rejected, Duplicate ID, 15 trips)
(31, 'Kavita Singh', '2024-11-17', '13:00:00', 'legal issue', NULL, NULL, NULL, 'rejected', 'Duplicate verification failed'),

-- Driver 32: Bharti Agarwal (auto, Surat, waitlisted, Extra charges complaints, 48 trips)
(32, 'Suresh Kumar', '2024-12-05', '15:30:00', 'rider issue', NULL, NULL, NULL, 'under_review', 'Extra charge complaints'),
(32, 'Meera Iyer', '2024-12-20', '11:45:00', 'rider issue', NULL, NULL, NULL, 'warning_issued', 'Behavior warning issued'),
(32, 'Ankit Sharma', '2024-12-23', '14:00:00', 'support issue', NULL, '2024-12-28', '10:00:00', 'pending', 'Compliance monitoring'),

-- Driver 33: Neha Kapoor (car, Mumbai, active, Low earning - night shift, 456 trips)
(33, 'Rahul Desai', '2024-12-09', '18:30:00', 'low earning', NULL, '2024-12-10', '20:00:00', 'resolved', 'Night shift priority enabled'),
(33, 'Priya Reddy', '2024-12-21', '14:00:00', 'support issue', NULL, '2024-12-21', '19:00:00', 'resolved', 'Platinum tier bonus confirmed'),
(33, 'Ankit Sharma', '2024-12-23', '16:30:00', 'low earning', NULL, '2024-12-24', '20:00:00', 'resolved', 'Airport runs optimized'),

-- Driver 34: Divya Krishnan (car, Hyderabad, active, Vehicle - AC malfunction, 389 trips)
(34, 'Kavita Singh', '2024-12-07', '11:20:00', 'vehicle issue', NULL, '2024-12-09', '08:00:00', 'resolved', 'AC repaired successfully'),
(34, 'Ankit Sharma', '2024-12-20', '15:45:00', 'rider issue', NULL, '2024-12-21', '10:00:00', 'resolved', 'Service quality training'),
(34, 'Meera Iyer', '2024-12-23', '13:20:00', 'support issue', NULL, '2024-12-24', '09:00:00', 'resolved', 'Performance review'),

-- Driver 35: Meera Devi (car, Lucknow, active, Health issue - back pain, 267 trips)
(35, 'Meera Iyer', '2024-12-11', '10:30:00', 'out of station', NULL, '2024-12-16', '09:00:00', 'approved', 'Medical leave approved'),
(35, 'Suresh Kumar', '2024-12-22', '14:20:00', 'call disconnect', 'followup', '2024-12-23', '10:00:00', 'resolved', 'Returned to service'),
(35, 'Priya Reddy', '2024-12-23', '16:00:00', 'support issue', NULL, '2024-12-24', '08:00:00', 'resolved', 'Health check completed'),

-- Driver 36: Shalini Reddy (car, Hyderabad, active, Low earning complaint, 412 trips)
(36, 'Meera Iyer', '2024-12-14', '09:50:00', 'low earning', NULL, '2024-12-15', '07:00:00', 'in_progress', 'Earnings analysis ongoing'),
(36, 'Rahul Desai', '2024-12-22', '13:30:00', 'low earning', NULL, '2024-12-23', '08:00:00', 'resolved', 'High-demand zones suggested'),
(36, 'Ankit Sharma', '2024-12-23', '15:15:00', 'low earning', NULL, '2024-12-24', '07:00:00', 'resolved', 'Peak hour optimization'),

-- Driver 37: Anita Deshmukh (car, Nagpur, active, Personal issue - child care, 334 trips)
(37, 'Ankit Sharma', '2024-12-08', '16:45:00', 'need other trip', NULL, '2024-12-09', '11:00:00', 'resolved', 'Intercity rides enabled'),
(37, 'Priya Reddy', '2024-12-20', '12:00:00', 'low demand', NULL, '2024-12-21', '08:00:00', 'resolved', 'School zone routes optimized'),
(37, 'Kavita Singh', '2024-12-23', '14:30:00', 'support issue', NULL, '2024-12-24', '10:00:00', 'resolved', 'Flexible schedule arranged'),

-- Driver 38: Pradeep Nair (car, Kochi, active, Vehicle - tire replacement, 298 trips)
(38, 'Kavita Singh', '2024-12-10', '11:15:00', 'vehicle issue', NULL, '2024-12-12', '09:00:00', 'resolved', 'Tires replaced'),
(38, 'Meera Iyer', '2024-12-21', '15:00:00', 'seasonal issue', NULL, '2024-12-22', '08:00:00', 'resolved', 'Monsoon tips provided'),
(38, 'Ankit Sharma', '2024-12-23', '10:45:00', 'support issue', NULL, '2024-12-24', '09:00:00', 'resolved', 'Regular check-in'),

-- Driver 39: Ravi Chandra (car, Visakhapatnam, active, None, 367 trips)
(39, 'Priya Reddy', '2024-12-13', '14:20:00', 'support issue', NULL, '2024-12-14', '08:00:00', 'resolved', 'Performance milestone reached'),
(39, 'Rahul Desai', '2024-12-22', '11:30:00', 'need other trip', NULL, '2024-12-23', '09:00:00', 'resolved', 'Premium ride access granted'),
(39, 'Ankit Sharma', '2024-12-23', '16:45:00', 'support issue', NULL, '2024-12-24', '08:00:00', 'resolved', 'Loyalty bonus explained'),

-- Driver 40: Prakash Shetty (car, Bangalore, active, Vehicle - engine servicing, 501 trips - TOP PERFORMER)
(40, 'Priya Reddy', '2024-12-05', '10:00:00', 'vehicle issue', NULL, '2024-12-07', '09:00:00', 'resolved', 'Engine service completed'),
(40, 'Ankit Sharma', '2024-12-16', '11:30:00', 'support issue', NULL, '2024-12-16', '14:00:00', 'resolved', 'Diamond tier benefits'),
(40, 'Suresh Kumar', '2024-12-23', '09:00:00', 'support issue', NULL, '2024-12-24', '08:00:00', 'pending', 'Annual bonus processing'),
(40, 'Rahul Desai', '2024-12-23', '15:30:00', 'low earning', NULL, '2024-12-24', '10:00:00', 'resolved', 'Premium airport access'),

-- Driver 41: Madhuri Sinha (car, Patna, applied, Application under review, 0 trips)
(41, 'Rahul Desai', '2024-12-17', '13:30:00', 'doc issue', NULL, NULL, NULL, 'in_progress', 'Documents under review'),
(41, 'Kavita Singh', '2024-12-22', '10:45:00', 'call disconnect', 'language issue', NULL, NULL, 'pending', 'Hindi support needed'),

-- Driver 42: Dinesh Pillai (car, Chennai, reactivation, Document - fitness certificate, 178 trips)
(42, 'Meera Iyer', '2024-12-02', '14:50:00', 'doc issue', NULL, NULL, NULL, 'pending', 'Fitness certificate expired'),
(42, 'Ankit Sharma', '2024-12-20', '11:00:00', 'doc issue', NULL, '2024-12-26', '08:00:00', 'in_progress', 'Certificate renewed'),
(42, 'Priya Reddy', '2024-12-23', '15:20:00', 'doc issue', NULL, '2024-12-27', '09:00:00', 'pending', 'Final verification stage'),

-- Driver 43: Radha Krishna (car, Hyderabad, active, Personal - relocation, 423 trips)
(43, 'Kavita Singh', '2024-12-13', '14:20:00', 'out of station', NULL, '2024-12-20', '10:00:00', 'in_progress', 'City transfer processing'),
(43, 'Meera Iyer', '2024-12-21', '10:45:00', 'out of station', NULL, '2024-12-28', '09:00:00', 'pending', 'Transfer approval pending'),
(43, 'Ankit Sharma', '2024-12-23', '13:50:00', 'support issue', NULL, '2024-12-29', '08:00:00', 'pending', 'Relocation assistance'),

-- Driver 44: Ajay Thakur (car, Shimla, active, Seasonal - winter tourism, 198 trips)
(44, 'Suresh Kumar', '2024-12-09', '12:30:00', 'seasonal issue', NULL, '2024-12-10', '09:00:00', 'resolved', 'Winter tourism surge'),
(44, 'Priya Reddy', '2024-12-19', '16:15:00', 'low demand', NULL, '2024-12-20', '08:00:00', 'resolved', 'Tourist routes optimized'),
(44, 'Rahul Desai', '2024-12-23', '11:00:00', 'seasonal issue', NULL, '2024-12-24', '09:00:00', 'resolved', 'Christmas season bonus'),

-- Driver 45: Mohan Das (car, Bhubaneswar, active, None, 312 trips)
(45, 'Ankit Sharma', '2024-12-12', '10:15:00', 'support issue', NULL, '2024-12-13', '08:00:00', 'resolved', 'Regular performance check'),
(45, 'Meera Iyer', '2024-12-21', '14:40:00', 'low demand', NULL, '2024-12-22', '09:00:00', 'resolved', 'Area optimization'),
(45, 'Priya Reddy', '2024-12-23', '16:00:00', 'support issue', NULL, '2024-12-24', '08:00:00', 'resolved', 'Milestone celebration'),

-- Driver 46: Kishore Kumar (car, Vijayawada, active, Health - eye checkup, 356 trips)
(46, 'Ankit Sharma', '2024-12-12', '09:20:00', 'out of station', NULL, '2024-12-15', '10:00:00', 'approved', 'Medical leave approved'),
(46, 'Rahul Desai', '2024-12-22', '13:45:00', 'call disconnect', 'followup', '2024-12-23', '09:00:00', 'resolved', 'Returned to service'),
(46, 'Kavita Singh', '2024-12-23', '15:30:00', 'support issue', NULL, '2024-12-24', '08:00:00', 'resolved', 'Health clearance confirmed'),

-- Driver 47: Brijesh Pandey (car, Kanpur, active, Low earning - switching peak hours, 234 trips)
(47, 'Suresh Kumar', '2024-12-10', '11:45:00', 'low earning', NULL, '2024-12-11', '07:00:00', 'resolved', 'Peak hour strategy'),
(47, 'Priya Reddy', '2024-12-20', '15:00:00', 'low earning', NULL, '2024-12-21', '08:00:00', 'resolved', 'Morning rush optimization'),
(47, 'Ankit Sharma', '2024-12-23', '12:30:00', 'low demand', NULL, '2024-12-24', '07:00:00', 'resolved', 'Commercial zone routes'),

-- Driver 48: Archana Iyer (car, Kochi, applied, Waiting for onboarding, 0 trips)
(48, 'Meera Iyer', '2024-12-15', '10:00:00', 'doc issue', NULL, NULL, NULL, 'in_progress', 'Onboarding process ongoing'),
(48, 'Ankit Sharma', '2024-12-22', '14:15:00', 'support issue', NULL, '2024-12-27', '09:00:00', 'pending', 'Training scheduled'),

-- Driver 49: Nitesh Agarwal (car, Mumbai, active, Vehicle - brake system, 489 trips)
(49, 'Kavita Singh', '2024-12-06', '15:30:00', 'vehicle issue', NULL, '2024-12-08', '08:00:00', 'resolved', 'Brake system repaired'),
(49, 'Meera Iyer', '2024-12-21', '11:40:00', 'accident', NULL, '2024-12-28', '10:00:00', 'in_progress', 'Minor accident, insurance claim'),
(49, 'Suresh Kumar', '2024-12-23', '14:00:00', 'accident', NULL, '2025-01-02', '09:00:00', 'pending', 'Vehicle repair ongoing'),

-- Driver 50: Shilpa Hegde (car, Bangalore, waitlisted, Multiple account operation, 78 trips)
(50, 'Suresh Kumar', '2024-12-04', '14:15:00', 'legal issue', NULL, NULL, NULL, 'under_investigation', 'Multiple accounts suspected'),
(50, 'Priya Reddy', '2024-12-19', '10:20:00', 'call disconnect', 'abusive words', NULL, NULL, 'escalated', 'Aggressive behavior'),
(50, 'Kavita Singh', '2024-12-23', '11:45:00', 'legal issue', NULL, NULL, NULL, 'warning_issued', 'Investigation continues'),

-- Driver 51: Ranjit Singh (car, Amritsar, active, Seasonal - festival rush, 401 trips)
(51, 'Rahul Desai', '2024-12-08', '12:00:00', 'seasonal issue', NULL, '2024-12-08', '16:00:00', 'resolved', 'Festival bonus activated'),
(51, 'Priya Reddy', '2024-12-19', '15:30:00', 'low earning', NULL, '2024-12-20', '08:00:00', 'resolved', 'Festival incentives explained'),
(51, 'Ankit Sharma', '2024-12-23', '13:20:00', 'seasonal issue', NULL, '2024-12-24', '08:00:00', 'resolved', 'Peak season optimization'),

-- Driver 52: Vaishali Chopra (car, Delhi, rejected, Duplicate ID, 41 trips)
(52, 'Suresh Kumar', '2024-11-15', '13:45:00', 'legal issue', NULL, NULL, NULL, 'rejected', 'Permanent suspension'),
(52, 'Kavita Singh', '2024-12-01', '10:30:00', 'call disconnect', 'abusive words', NULL, NULL, 'rejected', 'Appeal denied'),

-- Driver 53: Ganesh Murthy (car, Chennai, active, Personal - health insurance, 378 trips)
(53, 'Ankit Sharma', '2024-12-11', '16:00:00', 'out of station', NULL, '2024-12-17', '09:00:00', 'approved', 'Medical leave for insurance'),
(53, 'Meera Iyer', '2024-12-22', '12:30:00', 'call disconnect', 'followup', '2024-12-23', '10:00:00', 'resolved', 'Returned to service'),
(53, 'Priya Reddy', '2024-12-23', '15:45:00', 'support issue', NULL, '2024-12-24', '08:00:00', 'resolved', 'Health status confirmed'),

-- Driver 54: Sunil Kapoor (car, Bangalore, active, None, 445 trips)
(54, 'Ankit Sharma', '2024-12-12', '16:00:00', 'support issue', NULL, '2024-12-13', '08:00:00', 'resolved', 'Regular check-in'),
(54, 'Priya Reddy', '2024-12-22', '11:20:00', 'need other trip', NULL, '2024-12-22', '15:00:00', 'resolved', 'Airport preference enabled'),
(54, 'Rahul Desai', '2024-12-23', '14:30:00', 'support issue', NULL, '2024-12-24', '08:00:00', 'resolved', '400+ trips milestone'),

-- Driver 55: Preeti Agarwal (car, Mumbai, active, Low earning - peak hour strategy, 412 trips)
(55, 'Meera Iyer', '2024-12-11', '17:30:00', 'low earning', NULL, '2024-12-12', '07:00:00', 'resolved', 'Peak hour optimization'),
(55, 'Rahul Desai', '2024-12-20', '14:45:00', 'support issue', NULL, '2024-12-21', '10:00:00', 'resolved', 'Platinum upgrade'),
(55, 'Ankit Sharma', '2024-12-23', '16:15:00', 'low earning', NULL, '2024-12-24', '07:00:00', 'resolved', 'Premium zones assigned'),

-- Driver 56: Anil Verma (car, Delhi, active, Vehicle - suspension check, 367 trips)
(56, 'Kavita Singh', '2024-12-14', '10:30:00', 'vehicle issue', NULL, '2024-12-16', '09:00:00', 'resolved', 'Suspension repaired'),
(56, 'Suresh Kumar', '2024-12-23', '15:20:00', 'accident', NULL, '2025-01-02', '10:00:00', 'in_progress', 'Minor collision, repairs underway'),
(56, 'Priya Reddy', '2024-12-23', '17:00:00', 'accident', NULL, '2025-01-03', '09:00:00', 'pending', 'Insurance claim processing');

GO


SELECT 
    agent_name,
    COUNT(agent_name) AS total_connections
FROM agent_connections
GROUP BY agent_name;

--select drivers.driver_name,drivers.vehicle_name,agent_connections.agent_name,agent_connections.driver_issue,agent_connections.connect_date
from drivers
inner join agent_connections
on drivers.driver_id=agent_connections.driver_id

SELECT 
    agent_name,
    COUNT(resolution_status) AS winback
FROM agent_connections
WHERE resolution_status = 'resolved'
GROUP BY agent_name;


SELECT 
    d.driver_id,
    d.driver_name,
    COUNT(a.driver_id) AS total_connections
FROM drivers d
LEFT JOIN agent_connections a
    ON d.driver_id = a.driver_id
GROUP BY 
    d.driver_id,
    d.driver_name
ORDER BY 
    d.driver_id;

 SELECT 
    d.driver_id,
    d.driver_name,
    a.driver_issue,
    a.agent_name,
    COUNT(*) OVER (PARTITION BY d.driver_id) AS total_connections
FROM drivers d
LEFT JOIN agent_connections a
    ON d.driver_id = a.driver_id;

    
SELECT driver_issue, COUNT(*)
FROM agent_connections
GROUP BY driver_issue;

SELECT 
    driver_id,
    driver_name,
    vehicle_type,
    city,
    status,
    trip_taken,
    date_of_birth,
    DATEDIFF(YEAR, date_of_birth, GETDATE()) AS age,
    CASE 
        WHEN DATEDIFF(YEAR, date_of_birth, GETDATE()) < 18 THEN 'Underage'
        WHEN DATEDIFF(YEAR, date_of_birth, GETDATE()) BETWEEN 18 AND 25 THEN 'Young Adult'
        WHEN DATEDIFF(YEAR, date_of_birth, GETDATE()) BETWEEN 26 AND 40 THEN 'Adult'
        WHEN DATEDIFF(YEAR, date_of_birth, GETDATE()) BETWEEN 41 AND 60 THEN 'Middle Age'
        ELSE 'Senior'
    END AS age_category
FROM drivers;

