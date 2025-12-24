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
    trip_taken INT
    created_at DATETIME2 DEFAULT GETDATE(),
    updated_at DATETIME2 DEFAULT GETDATE()
);
GO

-- Insert 55+ Driver Records with diverse vehicle types
INSERT INTO drivers (driver_name, vehicle_type, vehicle_name, city, status, issue, trip_taken) VALUES
-- Bike drivers
('Rajesh Kumar', 'bike', 'Honda Activa', 'Bangalore', 'active', 'None', 245),
('Priya Sharma', 'bike', 'TVS Jupiter', 'Mumbai', 'active', 'Low earning concern', 189),
('Amit Patel', 'bike', 'Suzuki Access', 'Delhi', 'waitlisted', 'Asking extra money from customers', 45),
('Sunita Reddy', 'bike', 'Hero Maestro', 'Hyderabad', 'rejected', 'Duplicate ID found', 12),
('Vijay Singh', 'bike', 'Yamaha Fascino', 'Pune', 'applied', 'Under verification', 0),
('Mohammed Ali', 'bike', 'Honda Dio', 'Bangalore', 'active', 'Vehicle maintenance issue', 312),
('Kavita Nair', 'bike', 'TVS Ntorq', 'Kochi', 'active', 'Health issue - diabetes management', 156),
('Sneha Desai', 'bike', 'Suzuki Burgman', 'Ahmedabad', 'active', 'Personal issue - family emergency', 203),
('Anjali Verma', 'bike', 'Honda Activa 6G', 'Jaipur', 'applied', 'Documents under review', 0),
('Pooja Singh', 'bike', 'TVS Jupiter ZX', 'Delhi', 'active', 'None', 278),
('Pallavi Jain', 'bike', 'Hero Pleasure', 'Jaipur', 'active', 'Seasonal issue - tourist season', 167),
('Seema Roy', 'bike', 'Yamaha Ray ZR', 'Guwahati', 'reactivation', 'Document issue - bank details update', 89),

-- Auto drivers
('Lakshmi Iyer', 'auto', 'Bajaj RE Auto', 'Chennai', 'reactivation', 'Document issue - expired license', 134),
('Deepak Mehta', 'auto', 'Piaggio Ape', 'Mumbai', 'waitlisted', 'Operating multiple vehicles with different IDs', 67),
('Rahul Gupta', 'auto', 'Mahindra Alfa', 'Delhi', 'rejected', 'Duplicate ID - account suspended', 23),
('Karthik Rao', 'auto', 'TVS King', 'Bangalore', 'active', 'Seasonal issue - monsoon affecting rides', 289),
('Suresh Babu', 'auto', 'Bajaj Maxima', 'Chennai', 'reactivation', 'Document issue - insurance expired', 145),
('Arun Kumar', 'auto', 'Piaggio Ape City', 'Bangalore', 'waitlisted', 'Customer complaints - overcharging', 56),
('Ramesh Pillai', 'auto', 'Mahindra Treo', 'Kochi', 'rejected', 'Duplicate ID verification failed', 18),
('Sandeep Joshi', 'auto', 'Bajaj RE Compact', 'Pune', 'reactivation', 'Document issue - RC renewal pending', 112),
('Vikram Malhotra', 'auto', 'TVS King Deluxe', 'Chandigarh', 'applied', 'Background verification in progress', 0),
('Rekha Patel', 'auto', 'Piaggio Ape Auto', 'Ahmedabad', 'waitlisted', 'Multiple vehicle operation suspected', 72),
('Govind Sharma', 'auto', 'Mahindra Alfa Plus', 'Indore', 'active', 'Seasonal issue - wedding season high demand', 234),
('Manoj Tiwari', 'auto', 'Bajaj RE 4S', 'Varanasi', 'rejected', 'Duplicate ID - multiple accounts', 34),
('Harish Bhat', 'auto', 'TVS King Duramax', 'Mangalore', 'reactivation', 'Document issue - PAN card update needed', 98),
('Swati Kulkarni', 'auto', 'Piaggio Ape Xtra', 'Pune', 'waitlisted', 'Asking extra fare from passengers', 61),
('Nandini Rao', 'auto', 'Mahindra Treo Zor', 'Mysore', 'applied', 'Documents submitted', 0),
('Geeta Menon', 'auto', 'Bajaj RE Electric', 'Trivandrum', 'reactivation', 'Document issue - address proof pending', 87),
('Sanjay Mishra', 'auto', 'TVS King Electric', 'Bhopal', 'rejected', 'Duplicate ID found in system', 29),
('Naresh Yadav', 'auto', 'Piaggio Ape E-City', 'Delhi', 'waitlisted', 'Driving multiple vehicles with different IDs', 54),
('Usha Rani', 'auto', 'Mahindra Alfa Load', 'Ranchi', 'rejected', 'Duplicate ID verification failed', 15),
('Bharti Agarwal', 'auto', 'Bajaj Qute', 'Surat', 'waitlisted', 'Customer complaints about extra charges', 48),

-- Car drivers
('Neha Kapoor', 'car', 'Hyundai Creta', 'Mumbai', 'active', 'Low earning - night shift preference', 456),
('Divya Krishnan', 'car', 'Hyundai Venue', 'Hyderabad', 'active', 'Vehicle issue - AC malfunction', 389),
('Meera Devi', 'car', 'Toyota Etios', 'Lucknow', 'active', 'Health issue - back pain', 267),
('Shalini Reddy', 'car', 'Honda City', 'Hyderabad', 'active', 'Low earning complaint', 412),
('Anita Deshmukh', 'car', 'Toyota Innova', 'Nagpur', 'active', 'Personal issue - child care', 334),
('Pradeep Nair', 'car', 'Maruti Ertiga', 'Kochi', 'active', 'Vehicle issue - tire replacement needed', 298),
('Ravi Chandra', 'car', 'Hyundai Venue', 'Visakhapatnam', 'active', 'None', 367),
('Ashok Kumar', 'car', 'Toyota Etios', 'Coimbatore', 'active', 'Health issue - routine checkup', 289),
('Kavita Bose', 'car', 'Maruti Ertiga', 'Kolkata', 'active', 'Low earning due to area preference', 245),
('Prakash Shetty', 'car', 'Toyota Innova', 'Bangalore', 'active', 'Vehicle issue - engine servicing', 501),
('Madhuri Sinha', 'car', 'Hyundai Creta', 'Patna', 'applied', 'Application under review', 0),
('Dinesh Pillai', 'car', 'Honda City', 'Chennai', 'reactivation', 'Document issue - fitness certificate expired', 178),
('Radha Krishna', 'car', 'Maruti Dzire', 'Hyderabad', 'active', 'Personal issue - relocation planning', 423),
('Ajay Thakur', 'car', 'Hyundai Venue', 'Shimla', 'active', 'Seasonal issue - winter tourism', 198),
('Mohan Das', 'car', 'Toyota Etios', 'Bhubaneswar', 'active', 'None', 312),
('Kishore Kumar', 'car', 'Maruti Ertiga', 'Vijayawada', 'active', 'Health issue - eye checkup scheduled', 356),
('Brijesh Pandey', 'car', 'Honda Amaze', 'Kanpur', 'active', 'Low earning - switching to peak hours', 234),
('Archana Iyer', 'car', 'Maruti Dzire', 'Kochi', 'applied', 'Waiting for onboarding', 0),
('Nitesh Agarwal', 'car', 'Toyota Innova', 'Mumbai', 'active', 'Vehicle issue - brake system check', 489),
('Shilpa Hegde', 'car', 'Hyundai Creta', 'Bangalore', 'waitlisted', 'Multiple account operation suspected', 78),
('Ranjit Singh', 'car', 'Honda City', 'Amritsar', 'active', 'Seasonal issue - festival rush', 401),
('Vaishali Chopra', 'car', 'Maruti Swift', 'Delhi', 'rejected', 'Duplicate ID - policy violation', 41),
('Ganesh Murthy', 'car', 'Hyundai Venue', 'Chennai', 'active', 'Personal issue - health insurance claim', 378),
('Sunil Kapoor', 'car', 'Maruti Swift', 'Bangalore', 'active', 'None', 445),
('Preeti Agarwal', 'car', 'Honda Jazz', 'Mumbai', 'active', 'Low earning - peak hour strategy', 412),
('Anil Verma', 'car', 'Hyundai i20', 'Delhi', 'active', 'Vehicle issue - suspension check needed', 367);
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
